<script>
  import GithubIcon from "../../public/images/github.svg";
</script>

<style>
  .footer-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-bottom: 1rem;
  }

  @media (min-width: 767px) {
    .footer-container {
      display: none;
    }
  }
</style>

<div class="footer-container">
  <a class="github-link" href="https://github.com/raoufswe" target="blank">
    {@html GithubIcon}
  </a>
</div>
