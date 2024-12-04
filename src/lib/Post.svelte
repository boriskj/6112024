<script lang="ts">
	import type { UserPost } from '$lib';
	// import { Heart, ThumbsUp } from 'lucide-svelte';

	export let post: UserPost;
</script>

<div class="flex flex-col w-full">
	<div class="font-bold">{post.text}</div>
	<div class="w-full flex justify-between">
		<div class="">{new Date(post.timestamp).toLocaleString()}</div>
		<div>
			<div>{post.likes} 👍🏿</div>
			<!-- <ThumbsUp /> -->
		</div>
	</div>
</div>
