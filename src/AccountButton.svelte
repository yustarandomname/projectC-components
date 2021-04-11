<script>
  import Icon from "./Icon.svelte"

  export let user = false
  export const settings = false
</script>

<style>
  .button {
    width: 1em;
  }
</style>

{#if user}
  <p>logged in</p>
{:else}
  <div class="button" on:click={user = true}>
    <Icon name="person-circle-outline" />
  </div>
{/if}
