<script>
  import Nav from '../components/Nav.svelte';
  import Footer from '../components/Footer.svelte';
  export let segment;
</script>

<style>
  main {
    display: grid;

  }
</style>

<Nav {segment} />

<main>
  <slot></slot>
</main>

<Footer />