<script>
  export let name = "help-outline"
</script>

<style>
  .icon {
    height: 1.5em;
    width: 1.5em;
    background-size:contain;
    background-repeat: no-repeat;
  }
</style>

<slot>
  <ion-icon class="icon" name={name}></ion-icon>
</slot>