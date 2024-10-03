<script>
	import Navbar from "./sections/Navbar.svelte";

	let name = "";

	function onInputName(event) {
		name = event.target.value;
	}

	function resetClicked() {
		name = "";
	}
</script>

<Navbar title="vCard Generator" />

<form>
	<label>
		Name
		<input
			type="text"
			placeholder="Please enter your name"
			on:keydown={onInputName}
			bind:value={name}
		/>
	</label>
	<button
		type="reset"
		disabled={!name}
		on:click={resetClicked}
	>
		Reset
	</button>
</form>
