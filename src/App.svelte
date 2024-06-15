<script>
  import Router from "svelte-spa-router";
  import Home from "./pages/Home.svelte";
  import Maker from "./pages/Maker.svelte";
  import Play from "./pages/Play.svelte";
  import NotFound from "./pages/NotFound.svelte";
  import "./css/style.css";
  import Header from "./components/Header.svelte";

  const routes = {
    "/": Home,
    "/maker": Maker,
    "/play": Play,
    "*": NotFound,
  };
</script>

<Header />
<Router {routes} />
