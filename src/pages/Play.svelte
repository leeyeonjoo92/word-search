<script>
  const timer = () => {
    const startTime = new Date().getTime();

    const setTime = () => {
      const endTime = new Date().getTime();
      const passedTime = endTime - startTime;
      const min = Math.floor((passedTime / (1000 * 60)) % 60)
        .toString()
        .padStart(2, "0");
      const sec = Math.floor((passedTime / 1000) % 60)
        .toString()
        .padStart(2, "0");

      const puzzleTimer = document.querySelector(".puzzle-timer");
      puzzleTimer.textContent = `${min}:${sec}`;
    };

    setInterval(setTime, 1000);
  };

  const handleStart = (e) => {
    e.currentTarget.parentElement.style.display = "none";
    //name값이 입력됐는지 체크해야할듯

    // start 버튼 누르면 타이머 시작
    timer();
  };
</script>

<form id="play-user-form">
  <div class="play-user">
    <label for="user" class="user-label">Name</label>
    <input type="text" id="user" name="user" class="user-input" required />
  </div>
  <button type="submit" class="start-btn" on:click={handleStart}>Start</button>
</form>

<div class="puzzle-wrap">
  <div class="puzzle-info-wrap">
    <div class="puzzle-info">
      <span>제목</span>
      <span class="puzzle-timer">00:00</span>
    </div>
    <div class="puzzle-desc">설명</div>
  </div>
  <div class="puzzle-play">
    <div class="puzzle-word-list">
      {#each Array(10) as _, idx}
        <span id="puzzle-word{idx}" class="puzzle-word">단어</span>
      {/each}
    </div>
    <div class="puzzle-search">
      {#each Array(168) as _, idx}
        <span id="puzzle-alphabet{idx}" class="puzzle-alphabet">o</span>
      {/each}
    </div>
    <div class="puzzle-status-board">
      {#each Array(10) as _, idx}
        <div class="puzzle-status-user">
          <span id="puzzle-status-ranking{idx}" class="puzzle-status-ranking"
            >{idx + 1}위</span
          >
          <span id="puzzle-status-name{idx}" class="puzzle-status-score"
            >이름</span
          >
          <span id="puzzle-status-score{idx}" class="puzzle-status-score"
            >점수</span
          >
          <span id="puzzle-status-time{idx}" class="puzzle-status-time"
            >시간</span
          >
        </div>
      {/each}
    </div>
  </div>
</div>
