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
  form {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
  }

  label {
    display: flex;
    flex-grow: 0;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin-bottom: 8px;
  }

  input {
    border-radius: 8px;
    flex-grow: 1;
    margin-left: 8px;
  }

  .active {
    border-color: #ff9800;
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
