<script lang="ts" setup>
	import { Button, PrimaryHeading, Statistic, Text } from "@atoms";
	import { Statistics } from "@molecules";
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
		<Statistics>
			<Statistic label="Companies" value="2K+" />
			<Statistic label="Languages" value="8" />
			<Statistic label="Leads" value="1.2M" />
		</Statistics>
	</section>
</template>
