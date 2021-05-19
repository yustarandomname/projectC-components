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
  .positionTabs {
    white-space: nowrap;
    transition: transform 0.5s;
  }

  .tab {
    display: inline-block;
  }

  .tab:not(:first-child) {
    margin-left: 1em;
  }

  .tab:not(.tabSelected) {
    cursor: pointer;
  }
</style>

<Container {size} noStyle={true}>
  <div class="tabs">
    <div class="selectors">
      {#each tabs as tab, index}
        <div class="selector" class:selected={selected == index} on:click={() => selected = index}>
          {tab.title || tab.props.title}
        </div>
      {/each}
    </div>

    <div class="positionTabs" style="transform: translateX(-{41 * selected}em)">
      {#each tabs as tab, index}
        <div class="tab" class:tabSelected={selected == index} on:click={() => selected = index}>
          <Container {size} margin="0em">
            <svelte:component this={tab.component} {...tab.props} />
          </Container>
        </div>
      {/each}
    </div>
  </div>
</Container>