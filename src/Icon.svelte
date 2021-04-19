<svelte:head>
  <script src="https://unpkg.com/ionicons@5.4.0/dist/ionicons.js"></script>
</svelte:head>

<script>
  export let name = "help-outline"
</script>

<style>
  .icon {
    height: 1em;
    width: 1em;
    background-size:contain;
    background-repeat: no-repeat;
  }
</style>

<slot>
  <ion-icon class="icon" name={name}></ion-icon>
</slot>