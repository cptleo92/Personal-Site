<script>
  import BusinessCard from "./BusinessCard.svelte";
</script>

<section>
  <h1>Hello there!</h1>
  <h3>My name is</h3>

  <div class="arrow-container">
    <h2>Leo Cheng.</h2>

    <img class="arrow" src="images/vector-text.svg" alt="arrow" />
  </div>
  <p>
    I design, develop, and deploy full stack web applications. I love learning
    about trending technologies, experimenting with unfamiliar tools, and
    challenging myself by building outside of my comfort zone.
  </p>

  <BusinessCard />
</section>

<style>
  section {
    margin: 10rem auto;
    height: 90vh;
  }

  h1 {
    font-weight: 500;
    font-size: 3rem;
    color: #dbd8d8;
    margin-bottom: 1.6rem;
  }

  h2 {
    font-weight: 500;
    font-size: 2rem;
    color: #9ab4b9;
    margin-bottom: 0.5rem;
  }

  h3 {
    font-weight: 500;
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
  }

  p {
    font-weight: 300;
    font-size: 0.9rem;
  }

  .arrow-container {
    display: block;
    position: relative;
  }

  .arrow {
    position: absolute;
    left: 110px;
    top: -20px;
    width: 160px;
  }
</style>
