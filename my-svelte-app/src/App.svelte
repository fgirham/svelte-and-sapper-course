<script>
	import Navbar from "./sections/Navbar.svelte";
	import Form from "./components/Form.svelte";
	import VCard from "./components/VCard.svelte";

	let QRCode = "[YOUR NAME]";
	let values;
</script>

<Navbar title="vCard Generator" />

<main>
	<Form
		bind:values
		on:createQRCode={e => { QRCode = e.detail }}
	/>
	<VCard {values} {QRCode} />
</main>