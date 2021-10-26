<svelte:head>
	<!-- elements go here -->
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
</svelte:head>

<div class="flexBox">

	{#each config as item}
	<Frame height={item.height} width={item.width} src={item.src} bgstyle={item.bgstyle} alt={item.alt} title={item.title}
	 technology={item.technology} description={item.description} bind:itemTitle={titleText} bind:itemDesc={descText} />
	{/each}

</div>

<!--

<Modal bind:open={isOpenState}>
	<div class="modal-header">
		<h5 class="modal-title">{titleText}</h5>
		<button type="button" class="close" on:click={()=> (isOpenState = false)}>
			<span aria-hidden="true">&times;</span>
		</button>
	</div>
	<img src="images/flourish.svg" alt="flourish" class="flourish" />
	<div class="modal-body">{descText}</div>
</Modal>
-->



<!-- Import the counter component! -->
<script>
  import Fa from "svelte-fa/src/fa.svelte";
  import { faFlag } from "@fortawesome/free-solid-svg-icons";
  import config from "./config.json";
  import Modal from "sv-bootstrap-modal";
  import Frame from "./Frame.svelte";

  let isOpenState = false;

  $: titleText = null;
  $: descText = null;
</script>

<!-- Include styles -->
<style>
  @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css");

  :root {
    background-color: #f4f5f2;
  }

  :global(body) {
    background-color: #dadfd1;
    color: #004c72;
    background-image: url("data:image/svg+xml,%3Csvg width='30' height='30' viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M15 0C6.716 0 0 6.716 0 15c8.284 0 15-6.716 15-15zM0 15c0 8.284 6.716 15 15 15 0-8.284-6.716-15-15-15zm30 0c0-8.284-6.716-15-15-15 0 8.284 6.716 15 15 15zm0 0c0 8.284-6.716 15-15 15 0-8.284 6.716-15 15-15z' fill='%23f4f5f2' fill-opacity='0.4' fill-rule='evenodd'/%3E%3C/svg%3E");
    overflow: scroll;
  }

  :global(.modal-open) {
    overflow: hidden;
  }

  :global(.modal-header) {
    border: revert;
  }

  .flourish {
    width: 60%;
    height: 50%;
    padding: 6px;
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
    margin: 0 64px;
    padding-top: 64px;
    padding-bottom: 64px;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-around;
    align-content: center;
    /*background-color: #f4f5f2;*/
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