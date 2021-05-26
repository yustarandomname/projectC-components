<script>
  import Button from "../Button.svelte"

  export let value = false
  export let header = false
  export let footer = false
</script>

<style>
  :global(.checkbox ~ div) {
    margin: 0 !important;
  }

  :global(.checkbox ~ div input, .checkbox ~ div select) {
    margin: 0.5em 0 0;
    width: calc(100% - 2em - 2px);
  }

  .checkbox {
    position: relative;
  }

  .header { margin-top:1.4em; }
  .footer { margin-bottom: 2em}

  .header::before,
  .footer::after {
    color: #555;
    position: absolute;
    left: 0.6em;
  }

  .header::before {
    font-size: 0.5em;
    content: attr(data-header);
    top: -1.4em;
    font-weight: bold;
    text-transform: uppercase;
  }

  .footer::after {
    font-size: 0.7em;
    content: attr(data-footer);
    bottom: -1.2em;
    text-transform: lowercase;
  }
</style>

<div class="checkbox" class:header class:footer data-header={header} data-footer={footer} on:click={() => value = !value}>
  {#if value}
    <Button padding="0.4em" icon="radio-button-on-outline"/>
  {:else}
    <Button padding="0.4em" icon="radio-button-off-outline"/>
  {/if}
</div>