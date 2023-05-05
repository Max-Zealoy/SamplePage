<script>
  import { link } from "svelte-routing";

  //Handle error Image
  let logo = "/img/logo.svg";
  let fallbackLogo = "/img/logo.png";
  const handleError = (e) => (e.target.src = fallbackLogo);
</script>

<div class="nav">
  <a href="/" use:link class="logo">
    <img
      src={logo}
      alt="Brand logo"
      width="250"
      height="50"
      on:error={handleError}
    />
  </a>
  <div class="links">
    <a href="/page1" use:link class="page1">Page 1</a>
    <a href="/page2" use:link class="page2"> Page 2 </a>
    <a
      href="https://google.com"
      class="google"
      target="_blank"
      rel="noopener noreferrer">Google</a
    >
  </div>
</div>
