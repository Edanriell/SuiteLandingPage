<script lang="ts" setup>
	import { Copyright, Logotype, SocialLink } from "@atoms";
	import { SocialLinks } from "@molecules";
</script>

<template>
	<footer
		class="bg-[var(--colors-neutral-200)] pl-[32rem] pr-[32rem] pt-[71.2rem] pb-[40rem] flex flex-col items-center justify-center gap-y-[32rem] tablet:flex-row tablet:justify-between tablet:pt-[399.2rem] desktop:pl-[166.79rem] desktop:pr-[166.79rem] desktop:pt-[359.2rem] desktop:pb-[80rem]"
	>
		<Logotype />
		<Copyright />
		<SocialLinks>
			<SocialLink description="Link to our Facebook page" type="facebook" />
			<SocialLink description="Link to our Twitter page" type="twitter" />
			<SocialLink description="Link to our Instagram page" type="instagram" />
		</SocialLinks>
	</footer>
</template>
