<script lang="ts">
	import { page } from '$app/state';

	type PicturePost = {
		date: string,
		href: string
	}

	let posts = $derived(
		(page.data.posts || []).map((post: any) => ({
			date: post.meta.title,
			href: post.path
		} as PicturePost))
	);
</script>
<section class="primary">
    <h1>Pictures</h1>
</section>

