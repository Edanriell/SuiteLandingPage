<script lang="ts" setup>
	import { Motion, type VariantType } from "motion-v";

	interface LinkGhostProps {
		to: string;
	}

	const { to } = defineProps<LinkGhostProps>();

	const isLinkHovered = ref<boolean | null>(null);
	const isLinkPressed = ref<boolean | null>(null);

	const ghostLinkBackgroundVariants: Record<string, VariantType> = {
		displayed: {
			display: "block",
			y: ["100%", "0%"]
		},
		hidden: {
			y: ["0%", "-100%"]
		}
	};

	const ghostLinkPrimaryTextVariants: Record<string, VariantType> = {
		displayed: {
			y: ["0", "-100%"]
		},
		hidden: {
			y: ["100%", "0%"]
		}
	};

	const ghostLinkSecondaryTextVariants: Record<string, VariantType> = {
		displayed: {
			display: "block",
			y: ["100%", "0%"]
		},
		hidden: {
			y: ["0%", "-100%"]
		}
	};

	const animateLink = computed<keyof typeof ghostLinkBackgroundVariants | "">(() => {
		const hovered = isLinkHovered.value;
		const pressed = isLinkPressed.value;

		if (hovered === null && pressed === null) return "";

		if (hovered && !pressed) return "displayed";
		if (hovered && pressed) return "displayed";
		if (!hovered && pressed) return "displayed";
		if (!hovered && !pressed) return "hidden";
		if (pressed && !hovered) return "displayed";
		if (!pressed && !hovered) return "hidden";

		return "";
	});
</script>

<template>
	<NuxtLink :to="to">
		<Motion
			:transition="{ duration: 0.2 }"
			:whileFocus="{
				boxShadow:
					'0 0 0 3rem var(--colors-neutral-0), 0 0 0 6rem var(--colors-neutral-900)'
			}"
			:whileHover="{ scale: 1.1 }"
			:whilePress="{ scale: 0.95 }"
			as="div"
			class="relative overflow-hidden font-[Epilogue] bg-transparent font-bold text-[16rem] leading-[150%] tracking-[-0.01em] text-[var(--colors-neutral-900)] border-[1rem] border-solid border-[var(--colors-neutral-900)] rounded-[6rem] pt-[16rem] pb-[12rem] pl-[20rem] pr-[20rem] cursor-pointer focus:outline-none tablet:pl-[24rem] tablet:pr-[24rem]"
			@hoverEnd="() => (isLinkHovered = false)"
			@hoverStart="() => (isLinkHovered = true)"
			@press="() => (isLinkPressed = false)"
			@pressCancel="() => (isLinkPressed = false)"
			@pressStart="() => (isLinkPressed = true)"
		>
			<span class="relative overflow-hidden flex flex-col items center justify-center">
				<Motion
					:animate="animateLink"
					:initial="false"
					:transition="{ duration: 0.3 }"
					:variants="ghostLinkPrimaryTextVariants"
					as="span"
					class="z-3"
				>
					<slot />
				</Motion>
				<Motion
					:animate="animateLink"
					:initial="false"
					:transition="{ duration: 0.3 }"
					:variants="ghostLinkSecondaryTextVariants"
					as="span"
					class="hidden absolute text-[var(--colors-neutral-0)] z-2"
				>
					<slot />
				</Motion>
			</span>
			<Motion
				:animate="animateLink"
				:initial="false"
				:transition="{ duration: 0.2 }"
				:variants="ghostLinkBackgroundVariants"
				as="span"
				class="hidden absolute w-full h-full bg-[var(--colors-neutral-900)] top-0 left-0 z-1"
			/>
		</Motion>
	</NuxtLink>
</template>
