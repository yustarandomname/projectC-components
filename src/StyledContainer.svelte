<script>
  import { fade } from "svelte/transition";
  import Container from "./Container.svelte";
  export let size = "m";
  export let shadow = true
  export let data = { title: "please provide data" };
  export let minHeight = 0;
</script>

<style>
  h3 {
    margin: 0;
    margin-bottom: 0.5rem;
  }
</style>

<div transition:fade>
  <Container {size} {shadow}>
    <div style="min-height:{minHeight}">
      <h3>{data.title}</h3>
      <p>{data.content ? data.content : ''}</p>
    </div>
  </Container>
</div>
