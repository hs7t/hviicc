<script lang="ts">
	import { page } from '$app/state';
	import ImageGrid from '$lib/components/ImageGrid.svelte';

	type PicturePost = {
		date: string,
		href: string
	}

	let posts = $derived(
		(page.data.posts || []).map((post: any) => ({
			date: post.meta.date,
			href: post.meta.href,
            location: post.meta.location,
		} as PicturePost))
	);
</script>
<section class="primary">
    <h1>Pictures</h1>

    <section>
        <ImageGrid items={posts} />
    </section>
</section>

