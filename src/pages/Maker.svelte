<script>
  let clickSubmit = false;

  const handleSubmit = () => {
    clickSubmit = true;
  };
</script>

{#if !clickSubmit}
  <form id="maker-form">
    <div class="maker-inputs">
      <label for="title" class="maker-label">Title</label>
      <input type="text" id="title" name="title" class="maker-input" required />
    </div>
    <div class="maker-inputs">
      <label for="desc" class="maker-label">Description</label>
      <input
        type="textarea"
        id="desc"
        name="desc"
        class="maker-input"
        required
      />
    </div>
    <div class="maker-word-list-wrap">
      <div class="maker-label">Word List</div>
      <div class="maker-word-list">
        {#each Array(10) as _, idx}
          <input
            type="text"
            id="word${idx}"
            name="word${idx}"
            class="maker-input maker-word"
            required
          />
        {/each}
      </div>
    </div>
    <button type="submit" class="maker-submit-btn" on:click={handleSubmit}
      >Submit</button
    >
  </form>
{:else}
<div class="maker-updated-wrap">
  <div class="maker-updated-title">Puzzle Updated</div>
  <div class="maker-updated">
    <label for="maker-updated-link" class="maker-label">Play Link</label>
    <input
      type="text"
      id="maker-updated-link"
      name="maker-updated-link"
      class="maker-input"
      required
    />
  </div>
</div>
{/if}
