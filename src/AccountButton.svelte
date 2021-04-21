<script>
  import Button from "./Button.svelte"
import Icon from "./Icon.svelte"
  import Popup from "./Popup.svelte"

  export let user = {email: "user123@icloud.com", uid: "UH&9y8g4h94tgj39jdxc"}
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
  <p>{user.email}</p>
{:else}
  <div class="button" on:click={() => showAuth = true}>
    <Icon name="person-circle-outline" />
  </div>

  <Popup show={showAuth} on:exit={() => showAuth = false}>
    <h3>OAuth panel</h3>
    <Button on:click={() => user = {email: "user123@icloud.com", uid: "UH&9y8g4h94tgj39jdxc"}}>Log in as user123</Button>
  </Popup>
{/if}
