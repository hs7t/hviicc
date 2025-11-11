<script lang="ts">
	import { onMount } from "svelte"

    let Masonry: any
    let element: undefined | HTMLElement = undefined

	type GridItem = {
		location: string;
		date: string;
        href: string;
	};

    onMount(async () => {
        if (element) {
            Masonry = (await import('masonry-layout')).default;
            const imagesLoaded = (await import('imagesloaded')).default;

            let masonry = new Masonry(element, {
                itemSelector: '.grid-item',
                columnWidth: 200,
                gutter: 10
            });

            imagesLoaded(element, () => {
                masonry.layout();
            });
        }
    });

	let { items }: { items: Array<GridItem> } = $props();
</script>

<div class="image-grid" bind:this={element}>
	{#each items as item}
		<div class="grid-item">
            <img src={item.href} alt=""> <!-- TODO: ADD ALT TEXT!!! EXTREMELY IMPORTANT-->
		</div>
	{/each}
</div>

<style>
    .image-grid {
        width: 100%;
    }

	.grid-item {
        width: 200px;
        margin-bottom: 10px;
        height: auto;
    }

    .grid-item img {
        display: block;
        width: 100%;
    }
</style>