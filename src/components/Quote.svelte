<script>
  export let author;
  export let quote;
</script>

<style>
  .quote-container {
    background-color: #1e262f;
    padding: 32px;
    border-radius: 8px;
  }

  p {
    font-size: 1rem;
    font-weight: 500;
    line-height: 1.2;
    letter-spacing: 0.2px;
    color: #fff;
    min-height: 38px;
  }
  span {
    display: block;
    color: #fff;
    text-align: right;
    font-weight: 600;
    font-size: 0.9rem;
    font-style: italic;
  }

  .divider {
    width: 16px;
    height: 16px;
  }
</style>

<div class="quote-container">
  <p>{quote}</p>
  <div class="divider" />
  <span>- {author}</span>
</div>
