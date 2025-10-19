<script lang="ts" setup>
	import { Copyright, Logotype } from "@atoms";
	import { SocialLinks } from "@molecules";
</script>

<template>
	<footer
		class="ml-[32rem] mr-[32rem] pt-[56.2rem] pb-[40rem] flex flex-col items-center justify-center gap-y-[32rem] tablet:flex-row tablet:justify-between tablet:pt-[79.2rem] desktop:ml-[166.79rem] desktop:mr-[166.79rem] desktop:pt-[104.2rem] desktop:pb-[80rem]"
	>
		<Logotype />
		<Copyright />
		<SocialLinks />
	</footer>
</template>
