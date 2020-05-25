<script>
  import { onMount } from "svelte";
  import Quote from "./Quote.svelte";

  export let randomQuote;
  export let getRandomQuote;
</script>

<style>
  .random-section {
    margin: 0 auto;
    max-width: 400px;
    padding: 1rem 0;
  }

  .sub-title {
    font-size: 1.5rem;
    font-weight: 600;
    color: #fff;
    padding: 1rem 0;
    display: flex;
    align-items: center;
  }

  .random-icon {
    width: 50px;
    height: 50px;
    margin-left: 1rem;
    cursor: pointer;
  }

  @media (max-width: 767px) {
    .random-icon {
      margin-left: auto;
    }
  }
</style>

<section>
  <div class="sub-title">
    <span>Random Quote ✨</span>
    <img
      src="images/change.png"
      class="random-icon"
      alt="random"
      on:click={getRandomQuote} />
  </div>
  <div class="random-section">
    <Quote author={randomQuote.author} quote={randomQuote.en} />
  </div>
</section>
