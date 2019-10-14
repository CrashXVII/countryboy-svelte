<script>
  export let segment;
</script>

<style lang="scss">
  @import './styles/_variables.scss';

  nav {
    display: flex;
    flex-direction: column;
    text-align: center;
    /* justify-content: center; */
    align-content: center;
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    font-weight: 300;
    padding: 1em 0;
    color: $grey;

    @media screen and (min-width: $screen-md) {
      flex-direction: row;
      justify-content: space-between;
      margin: 0 1em;

    }
  }

  ul {
    list-style: none;
    display: flex;
    justify-content: space-around;
    margin: 0;
    padding: 0;

    li {}
  }

  a {
    text-decoration: none;
    color: $black;
  }

  .selected {
    position: relative;
    display: inline-block;
  }

  .selected::after {
    position: absolute;
    content: '';
    width: calc(100% - 1em);
    height: 2px;
    background-color: rgb(255, 62, 0);
    display: block;
    bottom: -1px;
  }
</style>

<nav>
  <a href=".">Country Boy Custom Birdhouses</a>
  <ul>
    <li><a class='{segment === undefined ? "selected" : ""}' href='.'>home</a></li>
    <li><a class='{segment === "about" ? "selected" : ""}' href='about'>about</a></li>

    <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
    <li><a rel=prefetch class='{segment === "blog" ? "selected" : ""}' href='blog'>gallery</a></li>
  </ul>
</nav>