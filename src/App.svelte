<script>
  import Header from "./lib/Header.svelte";
  import Intro from "./lib/Intro.svelte";
  import What from "./lib/What.svelte";
  import Where from "./lib/Where.svelte";
  import Who from "./lib/Who.svelte";
</script>

<Header />
<main>
  <Intro />
  <Who />
  <What />
  <Where />

  <hr />
  <footer>© 2023 Leo Cheng | Designed by Leo Cheng</footer>
</main>

<style>
  main {
    margin: 1.5rem 2rem;
  }

  footer {
    font-family: "Roboto Slab";
    font-style: normal;
    font-weight: 700;
    font-size: 1rem;
    text-align: center;
  }

  @media (min-width: 480px) {
    main {
      width: 400px;
      margin: 1.5rem auto;
    }
  }

  @media (min-width: 960px) {
    main {
      width: 720px;
      margin: 2rem auto;
    }
  }
</style>
