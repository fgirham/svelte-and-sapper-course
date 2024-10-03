<script>
	let name = "";
	let firstInput = "";

  let active = false;

	function onInputName(event) {
		name = event.target.value;
	}

	function resetClicked() {
		name = "";
		firstInput.focus();
	}
</script>

<style>
  .active {
    border-color: #ff9800;
    box-shadow: 0 1px 3px #f57c00;
    outline: none;
  }
</style>

<form>
	<label>
		Name
		<input
			type="text"
			placeholder="Please enter your name"
      class:active
      on:focus={() => active = true}
      on:blur={() => active = false}
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
