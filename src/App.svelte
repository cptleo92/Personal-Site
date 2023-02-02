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
    font-size: 12px;
    text-align: center;
  }

  @media (min-width: 480px) {
    main {
      margin: 1.5rem 4rem;
    }
  }
</style>
