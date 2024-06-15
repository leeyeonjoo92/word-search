<form>
  <div class="maker-inputs">
    <label for="title" class="maker-label">Title</label>
    <input type="text" id="title" name="title" class="maker-input" required />
  </div>
  <div class="maker-inputs">
    <label for="desc" class="maker-label">Description</label>
    <input type="text" id="desc" name="desc" class="maker-input" required />
  </div>
  <div class="maker-word-list">
    {#each Array(10) as _, idx}
      <input
        type="text"
        id="word${idx}"
        name="word${idx}"
        class="maker-word"
        required
      />
    {/each}
  </div>
  <button type="submit" class="maker-submit-btn">Submit</button>
</form>
