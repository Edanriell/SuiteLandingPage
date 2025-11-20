<script lang="ts" setup>
	import { Button, PrimaryHeading, Text } from "@atoms";
</script>

<template>
	<section
		class="ml-[16rem] mr-[16rem] pt-[40rem] pb-[285rem] tablet:ml-[32rem] tablet:mr-[32rem] tablet:pt-[48rem] tablet:pb-[266rem] tablet:grid tablet:grid-rows-1 tablet:grid-cols-[1fr_81rem_199rem] desktop:ml-[166rem] desktop:mr-[164rem] desktop:pt-[29rem] desktop:pb-[190rem] desktop:grid-cols-[1.7fr_161rem_189rem_1fr]"
	>
		<div
			class="flex flex-col tablet:col-start-[1] tablet:col-end-[3] tablet:row-start-[1] tablet:row-end-[2] tablet:z-2"
		>
			<PrimaryHeading
				after-bold="business."
				before="A"
				highlight="super"
				middle="for your"
				underlined="solution"
			/>
			<Text>
				Our marketing and sales automations help you scale your outreach to get more leads
				for your company.
			</Text>
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
		<div
			class="relative tablet:col-start-[1] tablet:col-end-[-1] tablet:mt-[80rem] desktop:mt-[unset] desktop:col-start-[unset] desktop:col-end-[unset] desktop:content-center"
		>
			<dl
				class="flex flex-col gap-y-[40rem] items-center tablet:grid tablet:gap-x-[64rem] tablet:grid-cols-[1fr_1fr_1fr] desktop:grid-cols-[unset] desktop:grid-rows-[86rem_86rem_86rem] desktop:gap-y-[64rem] desktop:gap-x-[unset] desktop:justify-end desktop:mr-[84rem]"
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
