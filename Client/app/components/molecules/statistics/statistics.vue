<script lang="ts" setup></script>

<template>
	<div
		class="relative tablet:col-start-[1] tablet:col-end-[-1] tablet:mt-[80rem] desktop:mt-[unset] desktop:col-start-[unset] desktop:col-end-[unset] desktop:content-center"
	>
		<dl
			class="flex flex-col gap-y-[40rem] items-center tablet:grid tablet:gap-x-[64rem] tablet:grid-cols-[1fr_1fr_1fr] desktop:grid-cols-[unset] desktop:grid-rows-[86rem_86rem_86rem] desktop:gap-y-[64rem] desktop:gap-x-[unset] desktop:justify-end desktop:mr-[84rem]"
		>
			<slot />
		</dl>
	</div>
</template>
