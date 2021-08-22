<div class="flexBox">

	<Frame height="360px" width="520px" bgstyle="default" src="https://willdebras.github.io/viz/img/portfolio/wine_region.svg"
	 alt="Wine region visualization" bind:isOpen={isOpenState} />

	<Frame height="300px" width="580px" bgstyle="lightblue" src="https://willdebras.github.io/viz/img/portfolio/empire.png" />
	<Frame height="450px" width="350px" bgstyle="lightblue" src="https://willdebras.github.io/viz/img/portfolio/voc_ed.png"
	 alt="infographic on vocational education" />
	<Frame height="450px" width="600px" src="https://willdebras.github.io/viz/img/portfolio/japan_perry_big.png" alt="elevation render of map" />
	<Frame height=" 320px" width="320px" src="https://raw.githubusercontent.com/willdebras/shotmaps/master/static/shot_map_knicks.png" />
	<Frame height="380px" width="600px" bgstyle="lightblue" alt="second" src="https://raw.githubusercontent.com/willdebras/viz/master/static/img/portfolio/mcbs.png" />

</div>

<Modal bind:open={isOpenState}>
	<div class="modal-header">
		<h5 class="modal-title">Modal title</h5>
		<button type="button" class="close" on:click={()=> (isOpen = false)}>
			<span aria-hidden="true">&times;</span>
		</button>
	</div>
	<div class="modal-body">Woohoo, you're reading this text in a modal!</div>
	<div class="modal-footer">
	</div>
</Modal>

<button class="btn btn-primary" on:click={()=> (isOpen = true)}>Open Modal</button>

<!-- Import the counter component! -->
<script>
  import Modal from "sv-bootstrap-modal";
  import Frame from "./Frame.svelte";

  let isOpenState = false;
</script>

<!-- Include styles -->
<style>
  @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css");

  :root {
    background-color: #f4f5f2 !important;
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