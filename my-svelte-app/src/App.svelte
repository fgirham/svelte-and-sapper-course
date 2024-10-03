<script>
	import Navbar from "./sections/Navbar.svelte";
	import Form from "./components/Form.svelte";
	import VCard from "./components/VCard.svelte";

	let QRCode = "";
</script>

<Navbar title="vCard Generator" />
<Form on:createQRCode={e => { QRCode = e.detail }}/>
<VCard {QRCode} />