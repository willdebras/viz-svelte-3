<script>
  export let height = "300px",
    width = "450px",
    bgstyle = "default",
    src = null,
    alt = "Will forgot to add alt text",
    isOpen = false;
</script>

<div {bgstyle} style="width:{width}; height:{height};"  on:click={()=> (isOpen = true)}>
  <img src={src} alt={alt} />
</div>


<style>
  div {
    border: 2px solid black;
    /*background-color: #ddc;*/
    border: solid 20px #eee;
    border-bottom-color: #fff;
    border-left-color: #eee;
    border-radius: 2px;
    border-right-color: #eee;
    border-top-color: #ddd;
    box-shadow: 0 0 5px 0 rgba(0, 0, 0, 0.25) inset,
      0 5px 10px 5px rgba(0, 0, 0, 0.25);
    box-sizing: border-box;
    text-align: center;
    position: relative;
    padding: 15px;
  }

  div:before {
    border-radius: 2px;
    bottom: -8px;
    box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.2) inset;
    content: "";
    left: -8px;
    position: absolute;
    right: -8px;
    top: -8px;
  }

  div:after {
    border-radius: 2px;
    bottom: -10px;
    box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.25);
    content: "";
    left: -10px;
    position: absolute;
    right: -10px;
    top: -10px;
  }

  img {
    /*border: solid 2px;*/
    border-bottom-color: #ffe;
    border-left-color: #eed;
    border-right-color: #eed;
    border-top-color: #ccb;
    height: 100%;
    width: 100%;
    max-width: 100%;
    object-fit: contain;
    display: block;
    margin: auto;
    filter: drop-shadow(0 -2px 0 #ccb) drop-shadow(0 2px 0 #ffe)
      drop-shadow(-2px 0 0 #eed) drop-shadow(2px 0 0 #eed);
  }
</style>