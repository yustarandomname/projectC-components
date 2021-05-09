<script>
  export let height = "1em"
</script>

<style>
  .loading {
    width:100%;
    position: relative;
  }

  .loadingAnimation {
    position:absolute;
    left:0%;
    height:100%;
    width:40%;
    background: rgb(219, 219, 219);
    background: linear-gradient(135deg, rgba(255,255,255,0) 10%, rgba(228,228,228,0.5) 20%, rgba(255,255,255,0) 100%);
    animation: loading 5s infinite;
  }

  @keyframes loading {
    from {left:0%}
    to {left:40%}
  }
</style>

<div class="loading" style="height:{height}">
  <div class="loadingAnimation"></div>
</div>