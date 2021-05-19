<script>
  import Container from "./Container.svelte"

  export let tabs = []
  export let size = "m"
  export let tabSize = "s"
  export let selected = 0
</script>

<style>
  :global(body) {
    overflow-x: hidden;
  }

  :global(.tab > .container) {
    max-width: 100%
  }

  /* SELECTORS */
  .selectors {
    display: flex;
    justify-content: center;
    padding:1em;
  }

  .selector {
    padding:0.5em 1em;
    margin: 0 0.5em;
    border: 1px solid black;
    border-radius: 1em;
    cursor: pointer;
  }

  .selected {
    color: white;
    background: var(--secondary, red)
  }

  /* TABS */

  .tabContainer {
    position:relative;
    height: 10em;
  }

  .positionTabs {
    width: 300%;
    display: flex;
    position: absolute;
    transition: left 0.5s;
  }

  .tab:not(:first-child) {
    margin-left: 1em;
  }
</style>

<Container {size} noStyle={true}>
  <div class="tabs">
    <div class="selectors">
      {#each tabs as tab, index}
        <div class="selector" on:click={() => selected = index} class:selected={selected == index}>{tab.props.title || tab.title}</div>
      {/each}
    </div>
    <div class="tabContainer">
      <div class="positionTabs" style="left: calc(-{selected * 40}em - {selected}em)">
        {#each tabs as tab}
          <div class="tab">
            <Container size={tabSize} margin="0em">
              <svelte:component this={tab.component} {...tab.props} />
            </Container>
          </div>
        {/each}
      </div>
    </div>
  </div>
</Container>