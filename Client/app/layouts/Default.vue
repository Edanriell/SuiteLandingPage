<script lang="ts" setup>
import Header from "~/components/organisms/header/header.vue";
import Footer from "~/components/organisms/footer/footer.vue";
</script>

<template>
	<Header />
	<main>
		<slot />
	</main>
	<Footer />
</template>