<style>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2rem 0;
    text-transform: uppercase;
    border-bottom: 1px dashed #fff;
    margin-bottom: 1rem;
  }

  h1 {
    color: #ff0a78;
    font-size: 2rem;
    font-weight: 600;
  }

  .links {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .link {
    text-decoration: none;
    color: #fff;
    font-weight: 600;
  }

  .link:first-of-type {
    margin-bottom: 10px;
  }

  .link:hover {
    color: #ff0a78;
  }

  @media (max-width: 767px) {
    h1 {
      font-size: 26px;
    }
    .links {
      display: none;
    }
  }
</style>

<header>
  <h1>Programming Quotes</h1>
  <div class="links">
    <a
      class="link"
      href="https://github.com/skolakoda/programming-quotes-api"
      target="blank">
      API
    </a>
    <a class="link" href="https://github.com/raoufswe" target="blank">GitHub</a>
  </div>

</header>
