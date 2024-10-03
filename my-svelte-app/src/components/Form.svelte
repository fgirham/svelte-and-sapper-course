<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  const defaultValues = {
    name: "",
    organisation: "",
    jobTitle: "",
    phone: "",
    address: "",
    email: "",
    photoURL: "https://i.pravatar.cc/100?img=68",
    logoURL: "https://icongr.am/entypo/database.svg?size=40&color=3d9afd",
    backgroundURL:
      "https://images.unsplash.com/photo-1523961131990-5ea7c61b2107?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1267&q=80"
  };

  export let values = { ...defaultValues };

  const inputsData = {
    name: {
      label: "Name",
      type: "text",
      placeholder: "Your contact name"
    },
    organisation: {
      label: "Organisation",
      type: "text",
      placeholder: "Name of your organisation"
    },
    jobTitle: {
      label: "Job Title",
      type: "text",
      placeholder: "Your job title"
    },
    phone: {
      label: "Phone number",
      type: "text",
      placeholder: "Your phone number"
    },
    address: {
      label: "Address",
      type: "text",
      placeholder: "Professional address"
    },
    email: {
      label: "E-Mail",
      type: "email",
      placeholder: "Professional E-Mail address"
    },
    photoURL: {
      label: "Photo",
      type: "text",
      placeholder: "URL of personal portrait"
    },
    logoURL: {
      label: "Company logo",
      type: "text",
      placeholder: "URL of your company's logo"
    },
    backgroundURL: {
      label: "Background image",
      type: "text",
      placeholder: "URL of card's background (leave blank for none)"
    }
  };

	let disabled = true;
	let firstInput;

  let active = {
    name: false,
    organisation: false,
    jobTitle: false,
    phone: false,
    address: false,
    email: false,
    photoURL: false,
    logoURL: false,
    backgroundURL: false
  };

	function keyPressed(event) {
    event.key === "Shift" ? "" : (disabled = false);
  }

	function resetClicked() {
    disabled = true;
    values = { ...defaultValues };
    firstInput.focus();
	}
</script>

<style>
  button {
    display: inline;
    border-radius: 8px;
    padding: 0.4rem 0.8rem;
  }
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

  .labelText {
    width: 15%;
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
    <div class="labelText">{inputsData.name.label}</div>
    <input
      type="text"
      placeholder={inputsData.name.placeholder}
      class:active={active.name}
      on:focus={() => {
        active.name = true;
      }}
      on:blur={() => {
        active.name = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.name}
      bind:this={firstInput} />
  </label>
  <label>
    <div class="labelText">{inputsData.organisation.label}</div>
    <input
      type="text"
      placeholder={inputsData.organisation.placeholder}
      class:active={active.organisation}
      on:focus={() => {
        active.organisation = true;
      }}
      on:blur={() => {
        active.organisation = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.organisation} />
  </label>
  <label>
    <div class="labelText">{inputsData.jobTitle.label}</div>
    <input
      type="text"
      placeholder={inputsData.jobTitle.placeholder}
      class:active={active.jobTitle}
      on:focus={() => {
        active.jobTitle = true;
      }}
      on:blur={() => {
        active.jobTitle = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.jobTitle} />
  </label>
  <label>
    <div class="labelText">{inputsData.phone.label}</div>
    <input
      type="text"
      placeholder={inputsData.phone.placeholder}
      class:active={active.phone}
      on:focus={() => {
        active.phone = true;
      }}
      on:blur={() => {
        active.phone = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.phone} />
  </label>
  <label>
    <div class="labelText">{inputsData.address.label}</div>
    <input
      type="text"
      placeholder={inputsData.address.placeholder}
      class:active={active.address}
      on:focus={() => {
        active.address = true;
      }}
      on:blur={() => {
        active.address = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.address} />
  </label>
  <label>
    <div class="labelText">{inputsData.email.label}</div>
    <input
      type="email"
      placeholder={inputsData.email.placeholder}
      class:active={active.email}
      on:focus={() => {
        active.email = true;
      }}
      on:blur={() => {
        active.email = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.email} />
  </label>
  <label>
    <div class="labelText">{inputsData.photoURL.label}</div>
    <input
      type="text"
      placeholder={inputsData.photoURL.placeholder}
      class:active={active.photoURL}
      on:focus={() => {
        active.photoURL = true;
      }}
      on:blur={() => {
        active.photoURL = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.photoURL} />
  </label>
  <label>
    <div class="labelText">{inputsData.logoURL.label}</div>
    <input
      type="text"
      placeholder={inputsData.logoURL.placeholder}
      class:active={active.logoURL}
      on:focus={() => {
        active.logoURL = true;
      }}
      on:blur={() => {
        active.logoURL = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.logoURL} />
  </label>
  <label>
    <div class="labelText">{inputsData.backgroundURL.label}</div>
    <input
      type="text"
      placeholder={inputsData.backgroundURL.placeholder}
      class:active={active.backgroundURL}
      on:focus={() => {
        active.backgroundURL = true;
      }}
      on:blur={() => {
        active.backgroundURL = false;
      }}
      on:keydown={keyPressed}
      bind:value={values.backgroundURL} />
  </label>
  <section>
    <button
      type="reset"
      {disabled}
      on:click={resetClicked}
    >
      Reset
    </button>
    <button
      type="submit"
      on:click|preventDefault={() => dispatch('createQRCode', 'QR Code goes here')}
    >
      Create QR Code
    </button>
  </section>
</form>
