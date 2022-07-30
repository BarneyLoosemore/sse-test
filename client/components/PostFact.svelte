<script lang="ts">
  let info = null;
  let source = null;

  const postFact = async () => {
    await fetch("http://localhost:3000/fact", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ info, source }),
    });
  };
</script>

<h1>Post fact:</h1>

<form style="display: flex; flex-direction: column; gap: 16px;">
  <input type="text" name="info" placeholder="info" bind:value={info} />
  <input type="text" name="source" placeholder="source" bind:value={source} />
  <button type="button" on:click={postFact}> Submit post </button>
</form>
