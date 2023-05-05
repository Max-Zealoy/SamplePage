<script>
  //Routing
  // @ts-ignore
  import { Router, Route } from "svelte-routing";

  //Import Pages
  import Home from "./pages/home.svelte";
  import Page1 from "./pages/page1.svelte";
  import Page2 from "./pages/page2.svelte";
  import ErrorPage from "./pages/errorPage.svelte";

  //Import Components
  import Nav from "./components/Nav.svelte";

  //This property is necessary avoiding that the Router is ignored
  export let url = "";
</script>

<Router {url}>
  <div class="main">
    <Nav />
    <Route exact path="/" component={Home} />
    <Route path="page1" component={Page1} />
    <Route path="page2" component={Page2} />
    <Route path="*" component={ErrorPage} />
  </div>
</Router>
