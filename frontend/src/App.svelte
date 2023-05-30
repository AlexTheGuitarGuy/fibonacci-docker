<script lang="ts">
  let indexInput = '';
  let indices = [1, 2, 3, 69, 420];

  function handleSubmit(event: InputEvent) {
    event.preventDefault();
    indexInput = '';
  }
</script>

<form class="form" on:submit={handleSubmit}>
  <label for="index">Index:</label>
  <input id="index" type="text" bind:value={indexInput} />

  <button type="submit">Submit</button>
</form>

<div style="margin-top: 3rem">
  <h3>Seen indices:</h3>
  {#each indices as number, index}
    <span>
      {number}{index !== indices.length - 1 ? ', ' : '.'}
    </span>
  {/each}
</div>

<div style="margin-top: 3rem">
  <h3>Calculated values:</h3>
  {#each indices as number, index}
    <div>
      for index {number}: {index % 2 ? 'bar' : 'foo'}
    </div>
  {/each}
</div>

<style>
  .form {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .form > * + * {
    margin-left: 1rem;
  }
</style>
