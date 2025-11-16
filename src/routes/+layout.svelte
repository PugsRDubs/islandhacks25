<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class ="center">
	<div class="main">
		<h1>Chips</h1>
		<p><strong>"Chipping" away at your tasks</strong></p>
		<p>To begin with this task tracker, make a class first. Choose a color and name for the class that you have tasks to complete. Then, add a task with a name, duration and due date. Finally, start tracking by clicking the duration ticker!</p>
		{@render children()}
	</div>
</div>




<style>
	:global(body) {
		background-color: rgb(237, 233, 216);
	}
	h1, h4 {
		margin-top: 0px;
		text-align: center;
		font-size: 60px;
		color: rgb(58, 58, 67);
		font-family: "Modak", system-ui;
		font-weight: 400;
		font-style: normal;
	}
	:global(h1, span, input, button) {
		color: rgb(80, 76, 68);
	}
	.center {
		display: flex;
		justify-content: center;
	}
	.main {
		width: 800px;
		margin: 40px;
		padding: 40px;
		background-color: rgb(214, 212, 198);
		border-style: none;
		border-width: 5px;
		border-radius: 5px;
		border-color:rgb(70, 70, 72);

	}
	:global(input, button, select, option) {
		border-style: none;
		background-color: rgba(214, 212, 198, 0.567);
		padding: 10px;
		border-radius: 10px;
		
	}
	:global(input, button, select, option, p, h1) {
		font-family: "Stack Sans Text", sans-serif;
		font-optical-sizing: auto;
		font-weight: 400;
		font-style: normal;
	}
</style>