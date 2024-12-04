<script lang="ts">
	import type { UserPost } from '$lib';
	import Post from '$lib/Post.svelte';
	import Page from '../+page.svelte';
	let posts: UserPost[] = [
		{ text: 'Hello World!', timestamp: Date.now(), likes: 0 },
		{ text: 'Hello World!', timestamp: Date.now(), likes: 0 }
	];
</script>

<div class="p-2 flex flex-col gap-4">
	{#each posts as p}
		<div class="flex gap-10 h-20 p-2 border-4 rounded-lg text-blue-100 border-cyan-700 bg-cyan-700">
			<Post post={p} />
		</div>
	{/each}
</div>
