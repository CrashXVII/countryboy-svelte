<style lang='scss'>
  .home {
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    justify-items: center;

    @media screen and (min-width: 768px) {
      font-size: 20px;
    }

    &-p {
      font-size: 3em;
    }
  }
</style>

<svelte:head>
  <title>Country Boy Custom Birdhouse</title>
</svelte:head>

<h1>Country Boy Custom Birdhouses</h1>
<div class="home">
  <p class="home-p">Sass Test be huge!</p>
</div>