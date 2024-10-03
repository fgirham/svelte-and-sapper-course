<script>
	let name = "";
	let firstInput = "";

	function onInputName(event) {
		name = event.target.value;
	}

	function resetClicked() {
		name = "";
		firstInput.focus();
	}
</script>

<form>
	<label>
		Name
		<input
			type="text"
			placeholder="Please enter your name"
			on:keydown={onInputName}
			bind:value={name}
			bind:this={firstInput}
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
