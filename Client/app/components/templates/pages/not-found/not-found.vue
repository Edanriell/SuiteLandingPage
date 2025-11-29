<script lang="ts" setup>
	import { Link } from "@atoms";
</script>

<template>
	<section
		class="font-[Epilogue] min-h-screen flex flex-col items-center justify-center text-center text-neutral-900 px-[16rem] bg-[#faf8f6] z-30 relative tablet:mb-[-359.200rem] desktop:mb-[-279.200rem]"
	>
		<h1 class="text-[96rem] font-extrabold leading-none tracking-tight mb-[16rem]">404</h1>
		<p class="text-[20rem] max-w-[480rem] text-neutral-600 mb-[32rem]">
			The page you’re looking for doesn’t exist or may have been moved.
		</p>
		<div class="flex gap-[16rem]">
			<Link to="/">&nbsp;&nbsp;Go Home&nbsp;&nbsp;</Link>
		</div>
	</section>
</template>
