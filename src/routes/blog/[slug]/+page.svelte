<script lang="ts">
	import { formatDate } from '$lib/utils';

	export let data;
</script>

<svelte:head>
	<title>{data.meta.title}</title>
	<meta property="og:type" content="article" />
	<meta property="og:title" content={data.meta.title} />
</svelte:head>

<article class="py-20 flex flex-col items-center">
	<div class="sm:px-0 max-w-xs sm:max-w-lg">
		<hgroup>
			<h1 class="text-3xl font-bold">{data.meta.title}</h1>
			<p class="text-gray-400">Published at {formatDate(data.meta.date)}</p>
		</hgroup>

		<div class="my-8">
			{#each data.meta.categories as category}
				<a
					href="/blog"
					class="rounded-full p-4 bg-gray-50 font-medium text-gray-600 hover:bg-gray-100"
					>{category}</a
				>
			{/each}
		</div>

		<div class="prose text-lg leading-loose hyphens-auto break-normal text-gray-700">
			<svelte:component this={data.content} />
		</div>
	</div>
</article>
