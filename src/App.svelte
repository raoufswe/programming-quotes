<script>
  import { onMount } from "svelte";
  import { paginate, PaginationNav } from "svelte-paginate";
  import Quote from "./components/Quote.svelte";
  import Header from "./components/Header.svelte";
  import Spinner from "./components/Spinner.svelte";
  import RandomQuote from "./components/RandomQuote.svelte";
  import Quotes from "./components/Quotes.svelte";
  import Footer from "./components/Footer.svelte";
  let quotes = [];
  let randomQuote = "";
  let quotesLoading = true;
  let randomQuotesLoading = true;

  const getQuotes = async () => {
    let response = await fetch(
      "https://programming-quotes-api.herokuapp.com/quotes/"
    );
    let data = await response.json();
    quotesLoading = false;
    return (quotes = data);
  };

  const getRandomQuote = async () => {
    let response = await fetch(
      "https://programming-quotes-api.herokuapp.com/quotes/random"
    );
    let data = await response.json();
    randomQuotesLoading = false;
    return (randomQuote = data);
  };

  onMount(() => {
    getQuotes();
    getRandomQuote();
  });
</script>

<style>
  main {
    padding: 0 2rem;
    margin: 0 auto;
    max-width: 1100px;
  }
  @media (max-width: 767px) {
    main {
      padding: 0 1rem;
    }
  }
</style>

<main>
  {#if quotesLoading || randomQuotesLoading}
    <Spinner />
  {:else}
    <Header />
    <RandomQuote {randomQuote} {getRandomQuote} />
    <Quotes {quotes} />
    <Footer />
  {/if}

</main>
