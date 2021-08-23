<div class="flexBox">

	{#each config as item}
	<Frame height={item.height} width={item.width} src={item.src} bgstyle={item.bgstyle} alt={item.alt} bind:isOpen={isOpenState} />
	{/each}

</div>

<Modal bind:open={isOpenState}>
	<div class="modal-header">
		<h5 class="modal-title">Modal title</h5>
		<button type="button" class="close" on:click={()=> (isOpenState = false)}>
			<span aria-hidden="true">&times;</span>
		</button>
	</div>
	<div class="modal-body">Woohoo, you're reading this text in a modal!</div>
	<div class="modal-footer">
	</div>
</Modal>


<!-- Import the counter component! -->
<script>
  import config from "./config.json";
  import Modal from "sv-bootstrap-modal";
  import Frame from "./Frame.svelte";

  let isOpenState = false;

  let bodyText = "test";
</script>

<!-- Include styles -->
<style>
  @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css");

  :root {
    background-color: #f4f5f2;
  }

  html,
  body {
    background-color: #f4f5f2;
  }

  h1,
  h2 {
    font-weight: 300;
    font-family: Lato;
  }

  .logo-font {
    text-transform: lowercase;
    font-size: 2.5rem;
    font-family: "Rajdhani", sans-serif;
    color: #aa1e1e;
  }

  .flexBox {
    display: flex;
    gap: 32px 24px;
    margin: 64px;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-around;
    align-content: center;
    background-color: #f4f5f2;
  }

  :global([bgstyle="default"]) {
    background-color: #ddc;
  }

  :global([bgstyle="lightblue"]) {
    background-color: #add8e6;
  }

  :global([bgstyle="lightyellow"]) {
    background-color: #f5f0bf;
  }
</style>