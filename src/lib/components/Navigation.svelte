<script lang="ts">
	let { id } = $props();
</script>

<nav class="navigation" {id}>
	<ul>
		<li><a href="/">About</a></li>
		<li><a href="/writing">Writing</a></li>
		<li><a href="/projects">Projects</a></li>
		<li><a href="/pictures">Pictures</a></li>
	</ul>
</nav>

<style>
	nav {
	}
	nav ul {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		overflow-y: auto;

		padding: 0.8rem;
		flex-grow: 1;

		border: var(--w-border-general);
		border-top: unset;
	}

	nav ul li {
		list-style: none;
	}
</style>
