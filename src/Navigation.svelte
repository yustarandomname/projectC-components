<script>
  import Container from "./Container.svelte"
  import AccountButton from "./AccountButton.svelte"

  export let title = "Project component"
  export let links = []
  export let background = "#34aeebee"
  
  export let authentication = false
  let authScreen = false
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
    width: 100%;
    position:fixed;
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
</style>

<div class="navigation">
  <nav>
    <Container {background}>
      <div class="navBar">
        <a href="./" class="appName">{title}</a>
  
        <div class="links">
          {#each links as link}
            <a href={link.url} class="link">{link.title}</a>
          {/each}

          {#if authentication}
            <div>
              <AccountButton on:click={() => authScreen == true}/>
            </div>
          {/if}
        </div>
      </div>
    </Container>
  </nav>
</div>
