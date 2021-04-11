<script>
  import { fade } from "svelte/transition";
  import Container from "./Container.svelte";
  export let size = "m";
  export let shadow = true
  export let data = { title: "please provide data" };
</script>

<style>
  h3 {
    margin: 0;
    margin-bottom: 0.5rem;
  }
</style>

<div transition:fade>
  <Container {size} {shadow}>
    <h3>{data.title}</h3>
    <p>{data.content ? data.content : ''}</p>
  </Container>
</div>
