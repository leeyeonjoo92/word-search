<script>
  const moveToMaker = (e) => {
    e.preventDefault();
    window.location.hash = "#/maker";
  };

  const moveToPlay = (e) => {
    e.preventDefault();
    window.location.hash = "#/play";
  };
</script>

<div class="home">
  <section class="home-maker">
    <div class="home-info">
      <img src="./src/assets/sample-puzzle.png" alt="sample-img" />
      <div class="home-desc">
        <div class="home-desc-title">Word Search</div>
        <p class="home-detail">
          <span
            >We have the best collection of word search puzzles online, with new
            ones being added regularly.</span
          >
          They are fun to play, but also educational, in fact, many teachers make
          use of them. <br />
          Puzzles are 100% free to play and work on desktop pc, mac, mobile and tablet.
          Or you can go old school and print them to enjoy offline later. <br />
          Plus, if you're feeling a little more adventurous, why not create your
          very own with our simple to use Word Search Maker, and then share them
          with your friends. <br />
          To get started playing, just select a game from below. Best of luck.
        </p>
        <a href="#/maker" on:click={moveToMaker} class="home-maker-btn"
          >Word Search Maker</a
        >
      </div>
    </div>
  </section>

  <section class="puzzle-list">
    <a href="#/play" on:click={moveToPlay} class="play-btn">Room</a>
    <a href="/" class="play-btn play-btn-empty">Empty</a>
    <a href="/" class="play-btn play-btn-empty">Empty</a>
  </section>
</div>
