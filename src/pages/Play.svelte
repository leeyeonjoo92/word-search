<script>
  import { onMount } from "svelte";

  /*----------------------------------------
   *		타이머 함수
   */
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

  /*----------------------------------------
   *		시작버튼 함수
   */
  const handleStart = (e) => {
    //name값이 입력됐는지 체크해야할듯
    e.currentTarget.parentElement.style.display = "none";

    // https://youtu.be/GMvv7RG7ulc?feature=shared&t=462
    const randomAlphabet = () => {
      const alphabets = document.querySelectorAll(".puzzle-alphabet");
      alphabets.forEach(function (alphabet) {
        if (alphabet.textContent != "") return;
        let charCode = Math.round(65 + Math.random() * 25);
        alphabet.textContent = String.fromCharCode(charCode);
      });
    };

    // start 버튼 누르면 타이머 시작
    timer();
  };

  /*----------------------------------------
   *		알파벳 랜덤 배치 함수
   */
  const randomAlphabet = () => {
    const alphabets = document.querySelectorAll(".puzzle-alphabet");
    alphabets.forEach(function (alphabet) {
      if (alphabet.textContent != "") return;
      let charCode = Math.round(65 + Math.random() * 25);
      alphabet.textContent = String.fromCharCode(charCode);

      alphabet.addEventListener("click", function (e) {
        alphabet.classList.add("correct1");
        console.log(alphabet);
      });
    });
  };

  // DOM에 마운트되는 즉시 실행
  onMount(() => randomAlphabet());

  // https://youtu.be/GMvv7RG7ulc?feature=shared&t=557
</script>

<!-- <form id="play-user-form">
  <div class="play-user">
    <label for="user" class="user-label">Name</label>
    <input type="text" id="user" name="user" class="user-input" required />
  </div>
  <button type="submit" class="start-btn" on:click={handleStart}>Start</button>
</form> -->

<div class="puzzle-wrap">
  <div class="puzzle-info-wrap">
    <div class="puzzle-info">
      <span>Room</span>
      <span class="puzzle-timer">00:00</span>
    </div>
    <div class="puzzle-desc">In my room.</div>
  </div>
  <div class="puzzle-play">
    <div class="puzzle-word-list">
      <!-- {#each Array(10) as _, idx}
        <span id="puzzle-word{idx}" class="puzzle-word">단어</span>
      {/each} -->
      <span id="puzzle-word0" class="puzzle-word">desk</span>
      <span id="puzzle-word1" class="puzzle-word">chair</span>
      <span id="puzzle-word2" class="puzzle-word">bed</span>
      <span id="puzzle-word3" class="puzzle-word">bookcase</span>
      <span id="puzzle-word4" class="puzzle-word">closet</span>
      <span id="puzzle-word5" class="puzzle-word">computer</span>
      <span id="puzzle-word6" class="puzzle-word">keyboard</span>
      <span id="puzzle-word7" class="puzzle-word">mouse</span>
      <span id="puzzle-word8" class="puzzle-word">headset</span>
      <span id="puzzle-word9" class="puzzle-word">fan</span>
    </div>
    <div class="puzzle-search">
      <!-- {#each Array(168) as _, idx}
        <span id="puzzle-alphabet{idx}" class="puzzle-alphabet">o</span>
      {/each} -->
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet">b</span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet">e</span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet">d</span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>

      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
      <span class="puzzle-alphabet"></span>
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
