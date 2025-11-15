<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div>
	<h1>Chips</h1>
</div>
<div>
	{@render children()}
</div>


<style>
	:global(body) {
		background-color: rgb(45, 47, 50);
		text-align: center;
		color:white
	}
	h1{
		text-align: center;
		font-family: 'Gill Sans', 'Gill Sans MT', 'Calibri', 'Trebuchet MS', sans-serif;
		font-size: 60px;
		color: rgba(235, 235, 243, 0.85);
	}
	div {
		margin: 40px;
		padding-bottom: 40px;
		background-color: rgb(45, 47, 50);
		border-style: solid;
		border-width: 5px;
		border-radius: 5px;
		border-color:rgb(70, 70, 72);

	}
</style>