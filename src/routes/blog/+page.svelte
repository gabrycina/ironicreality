<script lang="ts">
	import { formatDate } from '$lib/utils';
	import * as config from '$lib/config';

	export let data;
</script>

<svelte:head>
	<title>{config.title}</title>
</svelte:head>

<div class="bg-white py-24 sm:py-32">
	<div class="mx-auto max-w-4xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl lg:mx-0">
			<h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-7xl">Blog</h2>
		</div>
		<div
			class="mx-auto mt-10 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 border-t border-gray-200 pt-10 sm:mt-12 sm:pt-16 lg:mx-0 lg:max-w-none lg:grid-cols-3"
		>
			{#each data.posts as post}
				<article class="flex max-w-xl flex-col items-start justify-between">
					<div class="flex items-center gap-x-4 text-xs">
						<time datetime="2020-03-16" class="text-gray-500">{formatDate(post.date)}</time>
						{#each post.categories as category}
							<a
								href="/blog"
								class="relative z-10 rounded-full bg-gray-50 px-3 py-1.5 font-medium text-gray-600 hover:bg-gray-100"
								>{category}</a
							>
						{/each}
					</div>
					<div class="group relative">
						<h3
							class="mt-3 text-lg font-semibold leading-6 text-gray-900 group-hover:text-gray-600"
						>
							<a href={'/blog/' + post.slug}>
								<span class="absolute inset-0"></span>
								{post.title}
							</a>
						</h3>
						<p class="mt-5 line-clamp-3 text-sm leading-6 text-gray-600">
							{post.description}
						</p>
					</div>
				</article>
			{/each}
		</div>
	</div>
</div>
