<script>
  import Container from "./Container.svelte"
  import AccountButton from "./AccountButton.svelte"

  export let appName = "Project component"
  export let navItems = []
  export let background = "#34aeebee"
  export let authentication = true
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

  .navItem {
    margin-left: 1em;
  }
</style>

<div class="navigation">
  <nav>
    <Container {background}>
      <div class="navBar">
        <a href="./" class="appName">{appName}</a>
  
        <div class="navItems">
          {#each navItems as navItem}
            <a href={navItem.url} class="navItem">{navItem.title}</a>
          {/each}

          {#if authentication}
            <AccountButton />
          {/if}
        </div>
      </div>
    </Container>
  </nav>
</div>
