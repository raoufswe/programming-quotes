<script>
  import { onMount } from "svelte";
  import Quote from "./Quote.svelte";

  export let randomQuote;
  export let getRandomQuote;
</script>

<style>
  .random-section {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    align-items: center;
    justify-content: center;
  }

  .sub-title {
    font-size: 1.5rem;
    font-weight: 600;
    color: #fff;
    padding: 1rem 0 2rem;
  }

  .random-action-wrapper {
    text-align: center;
  }

  .random-icon {
    width: 60px;
    height: 60px;
    cursor: pointer;
    margin-top: 1rem;
  }

  .more {
    color: #fff;
    font-size: 24px;
  }

  @media (max-width: 767px) {
    .more {
      display: none;
    }
    .random-section {
      flex-direction: column;
    }
  }
</style>

<section>
  <div class="sub-title">
    <span>Random Quote ✨</span>
  </div>
  <div class="random-section">
    <Quote author={randomQuote.author} quote={randomQuote.en} />
    <div class="random-action-wrapper">
      <div class="more">Gimmme more 🕹️</div>
      <img
        src="images/change.png"
        class="random-icon"
        alt="random"
        on:click={getRandomQuote} />
    </div>

  </div>
</section>
