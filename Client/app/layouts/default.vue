<script lang="ts" setup>
import { Footer, Header } from "@organisms";
</script>

<template>
	<div>
		<Header />
		<main><slot /></main>
		<Footer />
	</div>
</template>
