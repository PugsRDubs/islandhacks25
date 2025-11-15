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
		background-color: rgb(217, 223, 229);
	}
	h1 {
		text-align: center;
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
		font-size: 60px;
		color: rgba(33, 33, 59,1);
	}
	div {
		margin: 20px;
		padding: 10px;
		background-color: rgb(177, 177, 193);
	}
</style>