<script>
  import { onMount, createEventDispatcher } from "svelte";
  import { paginate, PaginationNav } from "svelte-paginate";
  import Quote from "./Quote.svelte";
  export let quotes;
  let currentPage = 1;
  let pageSize = 4;
  $: paginatedQuotes = paginate({ items: quotes, pageSize, currentPage });
</script>

<style>
  .view-all {
    padding: 1rem 0;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    gap: 32px;
  }

  .sub-title {
    font-size: 1.5rem;
    font-weight: 600;
    color: #fff;
    padding: 1rem 0;
    display: flex;
    align-items: center;
  }

  .pagination-nav :global(.pagination-nav) {
    display: flex;
    justify-content: center;
    margin: 1rem 0;
  }
  .pagination-nav :global(.option) {
    padding: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: 0.2s all ease-out;
    user-select: none;
    color: #fff;
  }
  .pagination-nav :global(.option svg path) {
    fill: #fff;
  }
  .pagination-nav :global(.option:first-child) {
    border-radius: 3px 0 0 3px;
  }
  .pagination-nav :global(.option:last-child) {
    border-radius: 0 3px 3px 0;
  }
  .pagination-nav :global(.option.number),
  .pagination-nav :global(.option.ellipsis) {
    padding: 10px 15px;
  }
  .pagination-nav :global(.option:hover) {
    background: #000;
    cursor: pointer;
  }
  .pagination-nav :global(.option.active) {
    color: #ff0a78;
  }
</style>

<section>
  <div class="sub-title">All Quotes ✨</div>
  <div class="view-all">
    {#each paginatedQuotes as quote}
      <Quote author={quote.author} quote={quote.en} />
    {/each}
  </div>
</section>

<div class="pagination-nav">
  <PaginationNav
    totalItems={quotes.length}
    {pageSize}
    {currentPage}
    limit={1}
    showStepOptions={true}
    on:setPage={e => (currentPage = e.detail.page)} />
</div>
