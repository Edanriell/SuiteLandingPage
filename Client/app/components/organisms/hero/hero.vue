<script lang="ts" setup>
import { Button } from "@atoms";
</script>

<template>
	<section
		class="ml-[16rem] mr-[16rem] pt-[40rem] pb-[285rem] tablet:ml-[32rem] tablet:mr-[32rem] tablet:pt-[48rem] tablet:pb-[266rem] tablet:grid tablet:grid-rows-1 tablet:grid-cols-[1fr_81rem_199rem]"
	>
		<div
			class="flex flex-col tablet:col-start-[1] tablet:col-end-[3] tablet:row-start-[1] tablet:row-end-[2] tablet:z-2"
		>
			<h1
				class="font-[Epilogue] font-normal text-[38rem] leading-[110%] tracking-[-0.01em] text-[var(--colors-neutral-900)] mb-[24rem] tablet:text-[56rem] tablet:mb-[40rem] tablet:mt-[87rem]"
			>
				A
				<strong class="font-bold!"
					>super
					<span class="relative">
						<svg
							class="absolute top-[-24rem] left-[16rem] tablet:hidden"
							fill="none"
							height="17"
							viewBox="0 0 129 17"
							width="129"
							xmlns="http://www.w3.org/2000/svg"
						>
							<path
								d="M0.460449 15.2221C0.460449 15.2221 61.9093 -16.7779 128.016 15.2221"
								stroke="#172339"
								stroke-width="2"
							/>
						</svg>
						<svg
							class="hidden absolute top-[-52rem] left-[72rem] tablet:block"
							fill="none"
							height="34"
							viewBox="0 0 288 34"
							width="288"
							xmlns="http://www.w3.org/2000/svg"
						>
							<path
								d="M0.459717 32.9999C0.459717 32.9999 138.72 -39.0001 287.46 32.9999"
								stroke="#172339"
								stroke-width="2"
							/>
						</svg>
						solution
					</span></strong
				>
				for your
				<strong class="font-bold!">business.</strong>
			</h1>
			<p
				class="font-[Epilogue] font-normal text-[18rem] leading-[160%] tracking-[0.01em] text-[var(--colors-neutral-500)] mb-[40rem] tablet:mb-[48rem] tablet:max-w-[350rem]"
			>
				Our marketing and sales automations help you scale your outreach to get more leads
				for your company.
			</p>
			<Button class="w-[235rem]" variant="solid">Request Beta Access</Button>
		</div>
		<div
			class="relative mt-[64rem] mb-[64rem] tablet:col-start-[2] tablet:col-end-[4] tablet:row-start-[1] tablet:row-end-[2] tablet:mt-[unset] tablet:mb-[unset]"
		>
			<NuxtPicture
				class="block flex justify-center tablet:hidden"
				densities="x1 x2"
				format="avif,webp"
				height="240"
				quality="100"
				src="images/hero/phone_mobile.jpg"
				width="343"
			/>
			<NuxtPicture
				class="hidden tablet:block desktop:hidden"
				densities="x1 x2"
				format="avif,webp"
				height="480"
				quality="100"
				src="images/hero/phone_tablet.jpg"
				width="280"
			/>
			<NuxtPicture
				class="hidden desktop:block"
				densities="x1 x2"
				format="avif,webp"
				height="600"
				quality="100"
				src="images/hero/phone_desktop.jpg"
				width="350"
			/>
		</div>
		<div class="relative tablet:col-start-[1] tablet:col-end-[-1] tablet:mt-[80rem]">
			<dl
				class="flex flex-col gap-y-[40rem] items-center tablet:grid tablet:gap-x-[64rem] tablet:grid-cols-[1fr_1fr_1fr]"
			>
				<div
					class="flex flex-col-reverse gap-y-[4rem] items-center basis-x-[100%] tablet:basis-[192rem]"
				>
					<dt
						class="font-[Epilogue] font-normal text-[16rem] leading-[150%] tracking-[0.16em] uppercase text-[var(--colors-neutral-500)]"
					>
						Companies
					</dt>
					<dd
						class="font-[Epilogue] font-bold text-[48rem] leading-[120%] tracking-[-0.01em] uppercase text-[var(--colors-neutral-900)]"
					>
						2K+
					</dd>
				</div>
				<div class="flex flex-col-reverse gap-y-[4rem] items-center tablet:basis-[192rem]">
					<dt
						class="font-[Epilogue] font-normal text-[16rem] leading-[150%] tracking-[0.16em] uppercase text-[var(--colors-neutral-500)]"
					>
						Languages
					</dt>
					<dd
						class="font-[Epilogue] font-bold text-[48rem] leading-[120%] tracking-[-0.01em] uppercase text-[var(--colors-neutral-900)]"
					>
						8
					</dd>
				</div>
				<div class="flex flex-col-reverse gap-y-[4rem] items-center tablet:basis-[192rem]">
					<dt
						class="font-[Epilogue] font-normal text-[16rem] leading-[150%] tracking-[0.16em] uppercase text-[var(--colors-neutral-500)]"
					>
						Leads
					</dt>
					<dd
						class="font-[Epilogue] font-black text-[48rem] leading-[120%] tracking-[-0.01em] uppercase text-[var(--colors-neutral-900)]"
					>
						1.2M
					</dd>
				</div>
			</dl>
		</div>
	</section>
</template>
