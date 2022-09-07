<script>
	import Library from "./library/Library.svelte";

	function handleClick(id) {
		console.log('clicked ', id);
	}
</script>

<main>
	<Library onClick={handleClick} />
</main>

<style>
	
</style>