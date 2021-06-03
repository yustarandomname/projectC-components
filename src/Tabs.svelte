<script>
  import Container from "./Container.svelte"

  export let tabs = []
  export let size = "m"
  export let selected = 0

  $: modSelected = selected % tabs.length

  // initialize loaded with selected index + its neighbours
  let loaded = new Set()

  $: selected || setTab(selected)
  $: selected && setTab(selected)

  function setTab(index) {
    // set selected
    selected = index

    // load new index + its neigbours
    loaded.add(index)
    loaded.add(index + 1)
    loaded.add(index - 1)

    // change address of loaded to update UI
    loaded = new Set(Array.from(loaded))
  }
</script>

<style>
  :global(body) {
    overflow-x: hidden;
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
</style>

<Container {size} noStyle={true}>
  <div class="tabs">
    <div class="selectors">
      <slot name="tabBar">
        {#each tabs as tab, index}
          <div class="selector" class:selected={modSelected == index} on:click={() => setTab(index)}>
            {tab}
          </div>
        {/each}
      </slot>
    </div>

    <div class="positionTabs" style="transform: translateX(calc(-{100 * modSelected}% - {modSelected}em))">
      <slot/>
    </div>
  </div>
</Container>