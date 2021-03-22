<script>
	import Todos from './Todos.svelte';
</script>

<main>
	<h1>Zach's To-Do List</h1>
	<Todos />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		background-color:#16230D;
	}

	h1 {
		color: #713cd3;
		font-family: 'Source Code Pro', monospace;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>