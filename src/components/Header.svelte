<script>
  const moveToHome = (e) => {
    e.preventDefault();
    window.location.hash = "/";
  };

  const moveToMaker = (e) => {
    e.preventDefault();
    window.location.hash = "#/maker";
  };
</script>

<header>
  <a href="/" on:click={moveToHome}>Word Search Puzzles</a>
  <a href="#/maker" on:click={moveToMaker} class="header-icon"
    >word search maker</a
  >
</header>
