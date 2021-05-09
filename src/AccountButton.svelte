<script>
  import Popup from "./Popup.svelte"

  export let user;
  let showAuth = false
</script>

<style>
  .button {
    padding: 0.35em 0.35em 0.2em;
    border-radius: 0.5rem;
    cursor: pointer;
    box-shadow: 0 0 0.1rem rgb(0 0 0 / 10%);
    transition: 0.2s;
  }

  .button:hover {
    box-shadow: 0.1rem 0.1rem 1rem rgb(0 0 0 / 10%);
  }
</style>

{#if user}
  <div class="button" on:click>{user.email}</div>
{/if}
