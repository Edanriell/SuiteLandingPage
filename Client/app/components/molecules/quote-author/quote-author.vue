<script lang="ts" setup>
import { PersonName, PersonOccupation } from "@atoms";

interface QuoteAuthorProps {
		name: string;
		title: string;
	}

	const { name, title } = defineProps<QuoteAuthorProps>();
</script>

<template>
	<figcaption class="flex flex-col items-center desktop:items-start">
		<PersonName>{{ name }}</PersonName>
		<PersonOccupation>{{ title }}</PersonOccupation>
	</figcaption>
</template>
