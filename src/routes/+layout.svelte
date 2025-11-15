<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div>
	<h1>Awesome Project</h1>
</div>
<div>
	{@render children()}
</div>


<style>
	:global(body) {
		background-color: rgba(204, 215, 227, 1);
	}
	:global(h1) {
		text-align: center;
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
		font-size: 60px;
		color: rgba(33, 33, 59,1);
	
	}
	div {
		margin: 20px;
		padding: 10px;
		background-color: rgba(166, 166, 194, 1);
	}
</style>