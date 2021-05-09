<script>
  export let name = "help-outline";
  export let size = "1.5em";
</script>

<style>
  .icon {
    background-size:contain;
    background-repeat: no-repeat;
  }
</style>

<slot>
  <ion-icon class="icon" style="height:{size}; width:{size}" name={name}></ion-icon>
</slot>