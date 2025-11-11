<script lang="ts">
	import { page } from '$app/state';
	import ImageGrid from '$lib/components/ImageGrid.svelte';

	type PicturePost = {
		date: string,
		href: string
	}

	let posts = $derived(
		(page.data.posts || []).map((post: any) => ({
			date: post.meta.title,
			href: post.meta.href
		} as PicturePost))
	);
</script>
<section class="primary">
    <h1>Pictures</h1>

    <section>
        <ImageGrid items={posts} />
    </section>
</section>

