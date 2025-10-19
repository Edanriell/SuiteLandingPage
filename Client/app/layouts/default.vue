<script lang="ts" setup>
	import { Footer, Header } from "@organisms";
</script>

<template>
	<div class="bg-[#faf8f6] w-full">
		<Header />
		<main>
			<slot />
		</main>
		<Footer />
	</div>
</template>
