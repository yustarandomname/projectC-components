<script>
  import Container from "./Container.svelte"
  import AccountButton from "./AccountButton.svelte"

  export let title = "Project component"
  export let links = []
  export let background = "#34aeebee"
  
  export let user = false

  $: profileActions = false
    
</script>

<style>
  a {
    color: black;
    text-decoration: none;
  }

  a:hover,
  a:focus {
    text-decoration: underline;
  }

  .navigation {
    height: 6em
  }

  nav {
    left: 0;
    top: 1em;
    width: 100%;
    position: fixed;
    z-index: 10000;
  }

  .navBar{
    display: flex;
    align-items: center;
    justify-content:space-between;
  }

  .appName {
    font-size: 1.5rem;
    font-weight: bold;
  }

  .links {
    display: flex;
    align-items: center;
  }

  .links > * {
    margin-left: 1em;
  }

  /* Account actions */
  .accountActions {
    position:absolute;
    right:0;
    top: 4em;
    cursor:pointer
  }
</style>

<div class="navigation">
  <nav>
    <Container overflow="visible" {background}>
      <div class="navBar">
        <a href="./" class="appName">{title}</a>
  
        <div class="links">
          {#each links as link}
            <a href={link.url} class="link">{link.title}</a>
          {/each}

          {#if user}
            <AccountButton {user} on:click={() => profileActions = !profileActions}/>

            {#if profileActions && $$slots.accountActions}
              <div class="accountActions" on:click={() => profileActions = false}>
                <Container background="white">
                  <slot name="accountActions"/>
                </Container>
              </div>
            {/if}
          {/if}
        </div>
      </div>
    </Container>
  </nav>
</div>
