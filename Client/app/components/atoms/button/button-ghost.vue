<script lang="ts" setup>
	import { Motion, type VariantType } from "motion-v";

	interface ButtonGhostProps {
		type?: "button" | "submit" | "reset";
	}

	const { type = "button" } = defineProps<ButtonGhostProps>();

	const isButtonHovered = ref<boolean | null>(null);
	const isButtonPressed = ref<boolean | null>(null);

	const ghostButtonBackgroundVariants: Record<string, VariantType> = {
		displayed: {
			display: "block",
			y: ["100%", "0%"]
		},
		hidden: {
			y: ["0%", "-100%"]
		}
	};

	const ghostButtonPrimaryTextVariants: Record<string, VariantType> = {
		displayed: {
			y: ["0", "-100%"]
		},
		hidden: {
			y: ["100%", "0%"]
		}
	};

	const ghostButtonSecondaryTextVariants: Record<string, VariantType> = {
		displayed: {
			display: "block",
			y: ["100%", "0%"]
		},
		hidden: {
			y: ["0%", "-100%"]
		}
	};

	const animateButton = computed<keyof typeof ghostButtonBackgroundVariants | "">(() => {
		const hovered = isButtonHovered.value;
		const pressed = isButtonPressed.value;

		if (hovered === null && pressed === null) return "";

		// Hovered but unpressed
		if (hovered && !pressed) return "displayed";
		// Hovered and pressed
		if (hovered && pressed) return "displayed";
		// Unhovered and pressed
		if (!hovered && pressed) return "displayed";
		// Unhovered and unpressed
		if (!hovered && !pressed) return "hidden";
		// Pressed but not hovered (Mobile & Tablet)
		if (pressed && !hovered) return "displayed";
		// Unpressed and not hovered (Mobile & Tablet)
		if (!pressed && !hovered) return "hidden";

		return "";
	});
</script>

<template>
	<Motion
		:transition="{ duration: 0.2 }"
		:type="type"
		:whileFocus="{
			boxShadow: '0 0 0 3rem var(--colors-neutral-0), 0 0 0 6rem var(--colors-neutral-900)'
		}"
		:whileHover="{ scale: 1.1 }"
		:whilePress="{ scale: 0.95 }"
		as="button"
		class="relative overflow-hidden font-[Epilogue] bg-transparent font-bold text-[16rem] leading-[150%] tracking-[-0.01em] text-[var(--colors-neutral-900)] border-[1rem] border-solid border-[var(--colors-neutral-900)] rounded-[6rem] pt-[16rem] pb-[12rem] pl-[20rem] pr-[20rem] cursor-pointer focus:outline-none tablet:pl-[24rem] tablet:pr-[24rem]"
		@hoverEnd="() => (isButtonHovered = false)"
		@hoverStart="() => (isButtonHovered = true)"
		@press="() => (isButtonPressed = false)"
		@pressCancel="() => (isButtonPressed = false)"
		@pressStart="() => (isButtonPressed = true)"
	>
		<span class="relative overflow-hidden flex flex-col items center justify-center">
			<Motion
				:animate="animateButton"
				:initial="false"
				:transition="{ duration: 0.3 }"
				:variants="ghostButtonPrimaryTextVariants"
				as="span"
				class="z-3"
			>
				<slot />
			</Motion>
			<Motion
				:animate="animateButton"
				:initial="false"
				:transition="{ duration: 0.3 }"
				:variants="ghostButtonSecondaryTextVariants"
				as="span"
				class="hidden absolute text-[var(--colors-neutral-0)] z-2"
			>
				<slot />
			</Motion>
		</span>
		<Motion
			:animate="animateButton"
			:initial="false"
			:transition="{ duration: 0.2 }"
			:variants="ghostButtonBackgroundVariants"
			as="span"
			class="hidden absolute w-full h-full bg-[var(--colors-neutral-900)] top-0 left-0 z-1"
		/>
	</Motion>
</template>
