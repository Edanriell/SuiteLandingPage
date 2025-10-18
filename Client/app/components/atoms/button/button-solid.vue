<script lang="ts" setup>
import { animate, Motion, motionValue } from "motion-v";

interface ButtonSolidProps {
		type?: "button" | "submit" | "reset";
		initialColor?: string;
		initialGradientColors?: Array<string>;
		gradientColors?: Array<string>;
		animationDirection?: "left-to-right" | "right-to-left";
	}

	const {
		type = "button",
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
	} = defineProps<ButtonSolidProps>();

	const isButtonHovered = ref<boolean | null>(null);
	const isButtonPressed = ref<boolean | null>(null);

	const gradientColor1 = motionValue(initialColor);
	const gradientColor2 = motionValue(initialColor);
	const gradientColor3 = motionValue(initialColor);

	// Create reactive refs that update when motion values change
	const gradientColor1Value = ref(initialColor);
	const gradientColor2Value = ref(initialColor);
	const gradientColor3Value = ref(initialColor);

	// Subscribe to motion value changes
	gradientColor1.on("change", (v) => (gradientColor1Value.value = v));
	gradientColor2.on("change", (v) => (gradientColor2Value.value = v));
	gradientColor3.on("change", (v) => (gradientColor3Value.value = v));

	// Create a reactive object for background
	const background = computed(() => ({
		background: `linear-gradient(135deg, ${gradientColor1Value.value} 0%, ${gradientColor2Value.value} 49.21%, ${gradientColor3Value.value} 100%)`
	}));

	const animationFrame = ref<ReturnType<typeof setTimeout> | null>(null);
	const isAnimating = ref<boolean>(false);

	const startGradientAnimation = () => {
		if (isAnimating.value) return; // Already running
		isAnimating.value = true;

		// First gradient animation, which appears on hover
		// Animation starts from the initial solid color, to initial gradient colors (fallback is present)
		animate(gradientColor1, initialGradientColors[0] ?? "#a060ff", { duration: 0.2 });
		animate(gradientColor2, initialGradientColors[1] ?? "#cb30e3", { duration: 0.2 });
		animate(gradientColor3, initialGradientColors[2] ?? "#ffa84e", { duration: 0.2 });

		let colorIndex = 0;

		const animateNextShift = () => {
			if (!isAnimating.value) return;

			if (animationDirection === "right-to-left") {
				// Colors shift from right to left
				// color3 -> color2, color2 -> color1, new color -> color3
				const currentGradientColor1 = gradientColor2.get();
				const currentGradientColor2 = gradientColor3.get();
				const newGradientColor3 = gradientColors[(colorIndex + 3) % gradientColors.length];

				animate(gradientColor1, currentGradientColor1, { duration: 1, ease: "linear" });
				animate(gradientColor2, currentGradientColor2, { duration: 1, ease: "linear" });
				animate(gradientColor3, newGradientColor3!, { duration: 1, ease: "linear" });
			} else {
				// Colors shift from left to right
				// color1 -> color2, color2 -> color3, new color -> color1
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

		// Start the continuous animation after initial transition
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

	const animateButton = () => {
		const hovered = isButtonHovered.value;
		const pressed = isButtonPressed.value;

		if (hovered === null && pressed === null) return;

		// Hovered but unpressed
		if (hovered && !pressed) {
			startGradientAnimation();
			return;
		}
		// Hovered and pressed
		if (hovered && pressed) {
			startGradientAnimation();
			return;
		}
		// Unhovered and pressed
		if (!hovered && pressed) {
			startGradientAnimation();
			return;
		}
		// Unhovered and unpressed
		if (!hovered && !pressed) {
			stopGradientAnimation();
			return;
		}
		// Pressed but not hovered (Mobile & Tablet)
		if (pressed && !hovered) {
			startGradientAnimation();
			return;
		}
		// Unpressed and not hovered (Mobile & Tablet)
		if (!pressed && !hovered) {
			stopGradientAnimation();
			return;
		}
	};

	watch(isButtonHovered, animateButton);
	watch(isButtonPressed, animateButton);
</script>

<template>
	<Motion
		:style="background"
		:transition="{ duration: 0.2 }"
		:type="type"
		:whileFocus="{
			boxShadow: '0 0 0 3rem var(--colors-neutral-0), 0 0 0 6rem var(--colors-neutral-900)'
		}"
		:whileHover="{ scale: 1.1 }"
		:whilePress="{ scale: 0.95 }"
		as="button"
		class="font-[Epilogue] font-bold text-[16rem] leading-[150%] tracking-[-0.01em] text-[var(--colors-neutral-0)] rounded-[6rem] pt-[20rem] pb-[16rem] pl-[32rem] pr-[32rem] cursor-pointer focus:outline-none"
		@hoverEnd="() => (isButtonHovered = false)"
		@hoverStart="() => (isButtonHovered = true)"
		@press="() => (isButtonPressed = false)"
		@pressCancel="() => (isButtonPressed = false)"
		@pressStart="() => (isButtonPressed = true)"
	>
		<span><slot /></span>
	</Motion>
</template>
