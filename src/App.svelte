<script>
	import Library from "./library/Library.svelte";

	function handleBookSelect(id) {
		console.log('clicked ', id);
	}
</script>

<main>
	<Library onBookSelect={handleBookSelect} />
</main>

<style>
	
</style>