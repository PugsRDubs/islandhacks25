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
		background-color: rgba(232, 232, 232, 1);
	}
	h1{
		text-align: center;
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
		font-size: 60px;
		color: rgba(33, 33, 59, 0.85);
	
	#sub {
		text-align: center;
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
		font-size: 10px;
		color: rgba(22, 22, 39, 0.85);
	}
	}
	div {
		margin: 20px;
		padding: 10px;
		background-color: rgba(181, 181, 192, 1);

	}
</style>