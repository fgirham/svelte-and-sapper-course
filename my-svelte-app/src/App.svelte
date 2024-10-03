<script>
	import Navbar from "./sections/Navbar.svelte";

	let disabled = false;
</script>

<Navbar title="vCard Generator" />

<button {disabled}>Reset</button>