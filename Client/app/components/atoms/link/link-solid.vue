<script lang="ts" setup>
import { animate, Motion, motionValue } from "motion-v";

interface LinkSolidProps {
		to: string;
		initialColor?: string;
		initialGradientColors?: Array<string>;
		gradientColors?: Array<string>;
		animationDirection?: "left-to-right" | "right-to-left";
	}

	const {
		to,
		initialColor = "#172339",
		initialGradientColors = ["#a060ff", "#cb30e3", "#ffa84e"],
		gradientColors = [
			"#a060ff",
			"#cb30e3",
			"#ffa84e",
			"#ff6b6b",
			"#4ecdc4",
			"#45b7d1",
			"#f093fb",
			"#4facfe",
			"#00f2fe",
			"#feca57",
			"#48dbfb",
			"#a29bfe",
			"#55efc4",
			"#00b894"
		],
		animationDirection = "left-to-right"
	} = defineProps<LinkSolidProps>();

	const isLinkHovered = ref<boolean | null>(null);
	const isLinkPressed = ref<boolean | null>(null);

	const gradientColor1 = motionValue(initialColor);
	const gradientColor2 = motionValue(initialColor);
	const gradientColor3 = motionValue(initialColor);

	const gradientColor1Value = ref(initialColor);
	const gradientColor2Value = ref(initialColor);
	const gradientColor3Value = ref(initialColor);

	gradientColor1.on("change", (v) => (gradientColor1Value.value = v));
	gradientColor2.on("change", (v) => (gradientColor2Value.value = v));
	gradientColor3.on("change", (v) => (gradientColor3Value.value = v));

	const background = computed(() => ({
		background: `linear-gradient(135deg, ${gradientColor1Value.value} 0%, ${gradientColor2Value.value} 49.21%, ${gradientColor3Value.value} 100%)`
	}));

	const animationFrame = ref<ReturnType<typeof setTimeout> | null>(null);
	const isAnimating = ref<boolean>(false);

	const startGradientAnimation = () => {
		if (isAnimating.value) return;
		isAnimating.value = true;

		animate(gradientColor1, initialGradientColors[0] ?? "#a060ff", { duration: 0.2 });
		animate(gradientColor2, initialGradientColors[1] ?? "#cb30e3", { duration: 0.2 });
		animate(gradientColor3, initialGradientColors[2] ?? "#ffa84e", { duration: 0.2 });

		let colorIndex = 0;

		const animateNextShift = () => {
			if (!isAnimating.value) return;

			if (animationDirection === "right-to-left") {
				const currentGradientColor1 = gradientColor2.get();
				const currentGradientColor2 = gradientColor3.get();
				const newGradientColor3 = gradientColors[(colorIndex + 3) % gradientColors.length];

				animate(gradientColor1, currentGradientColor1, { duration: 1, ease: "linear" });
				animate(gradientColor2, currentGradientColor2, { duration: 1, ease: "linear" });
				animate(gradientColor3, newGradientColor3!, { duration: 1, ease: "linear" });
			} else {
				const newGradientColor1 = gradientColors[(colorIndex + 3) % gradientColors.length];
				const currentGradientColor2 = gradientColor1.get();
				const currentGradientColor3 = gradientColor2.get();

				animate(gradientColor1, newGradientColor1!, { duration: 1, ease: "linear" });
				animate(gradientColor2, currentGradientColor2, { duration: 1, ease: "linear" });
				animate(gradientColor3, currentGradientColor3, { duration: 1, ease: "linear" });
			}

			colorIndex = (colorIndex + 1) % gradientColors.length;
			animationFrame.value = setTimeout(animateNextShift, 500);
		};

		setTimeout(() => {
			if (isAnimating.value) {
				animateNextShift();
			}
		}, 300);
	};

	const stopGradientAnimation = () => {
		isAnimating.value = false;

		if (animationFrame.value !== null) {
			clearTimeout(animationFrame.value);
			animationFrame.value = null;
		}

		animateGradientToInitialSolidColor();
	};

	const animateGradientToInitialSolidColor = () => {
		animate(gradientColor1, initialColor, { duration: 0.2 });
		animate(gradientColor2, initialColor, { duration: 0.2 });
		animate(gradientColor3, initialColor, { duration: 0.2 });
	};

	const animateLink = () => {
		const hovered = isLinkHovered.value;
		const pressed = isLinkPressed.value;

		if (hovered === null && pressed === null) return;

		if (hovered && !pressed) {
			startGradientAnimation();
			return;
		}

		if (hovered && pressed) {
			startGradientAnimation();
			return;
		}

		if (!hovered && pressed) {
			startGradientAnimation();
			return;
		}

		if (!hovered && !pressed) {
			stopGradientAnimation();
			return;
		}

		if (pressed && !hovered) {
			startGradientAnimation();
			return;
		}

		if (!pressed && !hovered) {
			stopGradientAnimation();
			return;
		}
	};

	watch(isLinkHovered, animateLink);
	watch(isLinkPressed, animateLink);
</script>

<template>
	<NuxtLink :to="to">
		<Motion
			:style="background"
			:transition="{ duration: 0.2 }"
			:whileFocus="{
				boxShadow:
					'0 0 0 3rem var(--colors-neutral-0), 0 0 0 6rem var(--colors-neutral-900)'
			}"
			:whileHover="{ scale: 1.1 }"
			:whilePress="{ scale: 0.95 }"
			as="div"
			class="font-[Epilogue] font-bold text-[16rem] leading-[150%] tracking-[-0.01em] text-[var(--colors-neutral-0)] rounded-[6rem] pt-[20rem] pb-[16rem] pl-[32rem] pr-[32rem] cursor-pointer focus:outline-none"
			@hoverEnd="() => (isLinkHovered = false)"
			@hoverStart="() => (isLinkHovered = true)"
			@press="() => (isLinkPressed = false)"
			@pressCancel="() => (isLinkPressed = false)"
			@pressStart="() => (isLinkPressed = true)"
		>
			<span><slot /></span>
		</Motion>
	</NuxtLink>
</template>
