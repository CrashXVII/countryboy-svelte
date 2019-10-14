<script>
  export let segment;
</script>

<style lang="scss">
  @import './styles/_variables.scss';

  nav {
    display: flex;
    flex-direction: column;
    text-align: center;
    align-content: center;
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    font-weight: 300;
    padding: 1em 0;
    color: $grey;

    @media screen and (min-width: $screen-md) {
      flex-direction: row;
      text-align: start;
      justify-content: space-between;
      margin: 0 1em;

    }

    h4 {
      margin: 0;
      line-height: 1.5;
      text-transform: lowercase;
    }

    ul {
      list-style: none;
      display: flex;
      margin: 0;
      padding: 0;

      @media screen and (min-width: $screen-md) {}

      li {
        display: inline-block;
        position: relative;
        margin: 0 1.5em;

        a {
          &:after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background-color: red;
            visibility: hidden;
            transform: scaleX(0);
            transition: transform 0.2s ease;
          }

          &:hover:after,
          &:focus:after {
            visibility: visible;
            transform: scale(1);
          }

          &:focus {
            outline: none;
          }
        }
      }
    }
  }
</style>

<nav>
  <h4><a href=".">Country Boy Custom Birdhouses</a></h4>
  <ul>
    <li><a class='{segment === undefined ? "selected" : ""}' href='.'>home</a></li>
    <li><a class='{segment === "about" ? "selected" : ""}' href='about'>about</a></li>

    <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
    <li><a rel=prefetch class='{segment === "blog" ? "selected" : ""}' href='blog'>gallery</a></li>
  </ul>
</nav>