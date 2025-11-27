<script lang="ts" setup>
	import { SecondaryHeading } from "@atoms";
	import { PersonTestimonial } from "@molecules";
</script>

<template>
	<section
		class="relative rounded-[15rem] bg-[var(--colors-neutral-900)] pt-[345rem] pb-[40rem] px-[24rem] tablet:mx-[32rem] mb-[-15rem] tablet:px-[48rem] tablet:pb-[64rem] tablet:pt-[357rem] tablet:mb-[-320rem] desktop:grid desktop:grid-cols-2 desktop:grid-rows-1 desktop:gap-x-[160rem] desktop:py-[88rem] desktop:px-[125rem] desktop:mr-[164rem] desktop:ml-[167rem] desktop:mb-[-255rem]"
	>
		<div
			class="absolute w-[252rem] top-[-185rem] left-[50%] -translate-x-[50%] tablet:top-[-166rem] desktop:w-[360rem] desktop:relative desktop:top-[unset] desktop:left-[unset] desktop:translate-x-[unset] desktop:w-[unset] desktop:h-[unset] desktop:z-[20]"
		>
			<NuxtPicture
				class="relative block z-20 tablet:hidden"
				densities="x1 x2"
				format="avif,webp"
				height="412"
				quality="100"
				src="images/testimonial/person_mobile.png"
				width="252"
			/>
			<NuxtPicture
				class="relative hidden z-20 tablet:block desktop:hidden"
				densities="x1 x2"
				format="avif,webp"
				height="413"
				quality="100"
				src="images/testimonial/person_tablet.png"
				width="252"
			/>
			<NuxtPicture
				class="hidden w-[360rem] h-[590rem] z-20 desktop:block desktop:absolute desktop:bottom-[-88rem] desktop:left-[50%] desktop:translate-x-[-50%]"
				densities="x1 x2"
				format="avif,webp"
				height="590"
				quality="100"
				src="images/testimonial/person_desktop.png"
				width="360"
			/>
			<svg
				class="block z-10 w-[361rem] h-[518rem] absolute top-[40rem] left-[50%] -translate-x-[50%] tablet:hidden"
				fill="none"
				height="518"
				viewBox="0 0 375 518"
				width="375"
				xmlns="http://www.w3.org/2000/svg"
			>
				<g filter="url(#filter0_f_3_741)" opacity="0.476236">
					<circle cx="188" cy="258.914" fill="#CB30E3" r="123" />
				</g>
				<defs>
					<filter
						id="filter0_f_3_741"
						color-interpolation-filters="sRGB"
						filterUnits="userSpaceOnUse"
						height="517.828"
						width="517.828"
						x="-70.9141"
						y="-3.05176e-05"
					>
						<feFlood flood-opacity="0" result="BackgroundImageFix" />
						<feBlend
							in="SourceGraphic"
							in2="BackgroundImageFix"
							mode="normal"
							result="shape"
						/>
						<feGaussianBlur
							result="effect1_foregroundBlur_3_741"
							stdDeviation="67.957"
						/>
					</filter>
				</defs>
			</svg>
			<svg
				class="hidden z-10 w-[518rem] h-[518rem] absolute top-[60rem] left-[50%] -translate-x-[50%] tablet:block desktop:hidden"
				fill="none"
				height="518"
				viewBox="0 0 518 518"
				width="518"
				xmlns="http://www.w3.org/2000/svg"
			>
				<g filter="url(#filter0_f_3_559)" opacity="0.476236">
					<circle cx="258.914" cy="258.914" fill="#CB30E3" r="123" />
				</g>
				<defs>
					<filter
						id="filter0_f_3_559"
						color-interpolation-filters="sRGB"
						filterUnits="userSpaceOnUse"
						height="517.828"
						width="517.828"
						x="-3.05176e-05"
						y="-3.05176e-05"
					>
						<feFlood flood-opacity="0" result="BackgroundImageFix" />
						<feBlend
							in="SourceGraphic"
							in2="BackgroundImageFix"
							mode="normal"
							result="shape"
						/>
						<feGaussianBlur
							result="effect1_foregroundBlur_3_559"
							stdDeviation="67.957"
						/>
					</filter>
				</defs>
			</svg>
			<svg
				class="hidden z-10 absolute w-[566rem] h-[566rem] top-[5rem] left-[50%] translate-x-[-50%] desktop:block"
				fill="none"
				height="566"
				viewBox="0 0 566 566"
				width="566"
				xmlns="http://www.w3.org/2000/svg"
			>
				<g filter="url(#filter0_f_2_195)" opacity="0.476236">
					<circle cx="282.914" cy="282.914" fill="#CB30E3" r="147" />
				</g>
				<defs>
					<filter
						id="filter0_f_2_195"
						color-interpolation-filters="sRGB"
						filterUnits="userSpaceOnUse"
						height="565.828"
						width="565.828"
						x="0"
						y="-3.05176e-05"
					>
						<feFlood flood-opacity="0" result="BackgroundImageFix" />
						<feBlend
							in="SourceGraphic"
							in2="BackgroundImageFix"
							mode="normal"
							result="shape"
						/>
						<feGaussianBlur
							result="effect1_foregroundBlur_2_195"
							stdDeviation="67.957"
						/>
					</filter>
				</defs>
			</svg>
			<svg
				class="absolute bottom-[-81rem] left-[78rem] z-20 tablet:bottom-[-82rem] desktop:left-[unset] desktop:right-[-116rem] desktop:top-[73.5rem]"
				fill="none"
				height="54"
				viewBox="0 0 66 54"
				width="66"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					d="M64.2317 0.153564C64.2317 0.153564 57.85 41.4278 0.182838 52.1536"
					stroke="#FAF8F6"
					stroke-width="2"
				/>
			</svg>
		</div>
		<div class="relative">
			<SecondaryHeading before="It just " bold="works." />
			<PersonTestimonial
				name="Jeremy Robinson"
				quote="I really like how it is an all-in-one solution that handle many of the tasks that you would normally need separate tools to do the same job. This thing is a miracle worker."
				title="CMO, Fylo"
			/>
		</div>
		<div
			class="hidden desktop:block w-full h-[100rem] absolute bg-[var(--colors-neutral-200)] bottom-[-100rem] z-30"
		></div>
	</section>
</template>
