<script>
  import { onMount } from "svelte";
  import { fade, fly } from "svelte/transition";
  import Navbar from "./lib/Navbar.svelte";

  let ready = false;
  onMount(() => (ready = true));
</script>

{#if ready}
<Navbar />

  <!-- <img
    in:fly={{ y: 50, duration: 1000 }}
    class="avatar"
    src="images/avatar.jpg"
    alt="avatar"
  /> -->

  <div class="intro-container" in:fly={{ y: 50, delay: 1000, duration: 1000 }}>
    <header>
      <h4 class="intro">Nice to meet you! My name is</h4>
      <h2 class="myname">Leo Cheng.</h2>
      <p>I am a software engineer based in NYC.</p>
    </header>
  </div>
{/if}

<style>
  .avatar {
    border-radius: 50%;
    width: 300px;
    height: 300px;
    display: block;
    margin: 50px auto;
    border: 8px solid rgb(143, 143, 248);
  }

  .intro-container {
    /* display: block; */
    /* width: 400px; */
    /* margin: auto; */
    text-align: center;
  }

  .intro {
    font-size: 1.5rem;
  }

  .myname {
    font-size: 4rem;
    color: white;
  }
</style>
