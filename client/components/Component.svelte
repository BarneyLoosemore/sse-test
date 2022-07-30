<script lang="ts">
  let facts: { info: string; source: string }[] = [];
  const events = new EventSource("http://localhost:3000/events");
  events.onmessage = (event) => {
    const parsedData = JSON.parse(event.data);
    facts = facts.concat(parsedData);
  };
</script>

<h1>Facts</h1>
<ul>
  {#each facts as fact}
    <li>
      <p>{fact.info}</p>
      <p>{fact.source}</p>
    </li>
  {/each}
</ul>
