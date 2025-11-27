<script lang="ts" setup>
import { Quote } from "@atoms";

import QuoteAuthor from "../quote-author/quote-author.vue";

interface PersonTestimonialProps {
		quote: string;
		name: string;
		title: string;
	}

	const { quote, name, title } = defineProps<PersonTestimonialProps>();
</script>

<template>
	<figure class="relative desktop:mr-[5rem]">
		<Quote>{{ quote }}</Quote>

		<QuoteAuthor :name="name" :title="title" />
	</figure>
</template>
