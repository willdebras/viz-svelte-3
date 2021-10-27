<script>
  export let height = "300px",
    width = "450",
    widthLarge = "600",
    bgstyle = "default",
    src = null,
    alt = "Will forgot to add alt text",
    isOpen = false,
    title = null,
    technology = null,
    description = null,
    itemTitle = null,
    itemTech = null,
    itemDesc = null;

  function modalData() {
    (isOpen = !isOpen),
      (itemTitle = title),
      (itemTech = technology),
      (itemDesc = description);
    window.scrollTo({ top: 0 });
    window.document.body.classList.toggle("modal-open");
  }
</script>
<div class="{ isOpen ? 'openWrapper' : '' }" >
<button class = "buttonClosed { isOpen ? 'buttonViz' : '' }" on:click={modalData}>
Back to gallery
</button>
<div style = "flex-basis:100%;"></div>
  <div class = "{ isOpen ? 'frameOpen' : 'frame' }" {bgstyle} 
  style="width:{isOpen ? widthLarge + 'px' : width + 'px'}; height:{isOpen ? 'auto' : height + 'px'};"  
        on:click={modalData}>
    <img src={src} alt={alt} />
  </div>
  <div class="{ isOpen ? 'titleDiv' : 'closedDiv'}">
  <h5>{title}</h5>
  <hr>
  {description}
  </div>

</div>


<style>
  hr {
    border: none;
    color: #004c72;
    border-top: 3px double #004c72;
    overflow: visible;
    text-align: left;
    height: 3px;
    max-width: 400px;
    margin: auto 0;
    margin-bottom: 10px;
  }
  .closedDiv {
    transform: scale(0, 0);
    width: 0;
    height: 0;
  }

  .titleDiv {
    transform: scale(1, 1);
    flex: 1;
    margin-top: 12px;
  }

  .buttonClosed {
    transform: scale(0, 0);
  }
  .buttonViz {
    transform: scale(1, 1);
    padding: 8px;
    border: 0;
    margin: 15px;
    border-radius: 5px;
    border: 1px solid #add8e6;
  }
  .frame {
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

  .frame:before {
    border-radius: 2px;
    bottom: -8px;
    box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.2) inset;
    content: "";
    left: -8px;
    position: absolute;
    right: -8px;
    top: -8px;
  }

  .frame:after {
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

  .openWrapper {
    position: absolute;
    z-index: 999999;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    width: XXXpx; /*otherwise div defaults to page width*/
    height: 100%;
    padding: 64px;
    display: flex;
    align-items: flex-start;
    align-content: flex-start;
    gap: 64px;
    flex-wrap: wrap;
    margin: auto; /*horizontally centers div*/
    background-color: #dadfd1;
    overflow-y: hidden;
    color: #004c72;
    background-image: url("data:image/svg+xml,%3Csvg width='30' height='30' viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M15 0C6.716 0 0 6.716 0 15c8.284 0 15-6.716 15-15zM0 15c0 8.284 6.716 15 15 15 0-8.284-6.716-15-15-15zm30 0c0-8.284-6.716-15-15-15 0 8.284 6.716 15 15 15zm0 0c0 8.284-6.716 15-15 15 0-8.284 6.716-15 15-15z' fill='%23f4f5f2' fill-opacity='0.4' fill-rule='evenodd'/%3E%3C/svg%3E");
  }

  .frameOpen {
    border: 4px solid #ddc;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px,
      rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
  }
</style>