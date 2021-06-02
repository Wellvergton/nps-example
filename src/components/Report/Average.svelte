<script>
  import { onMount } from "svelte";
  import dummyClients from "../../dummyClients.js";
  
  let average;
  
  onMount(() => {
    let total = 0;
    
    dummyClients.forEach((client) => total += client.npsGrade);
    
    average = (total / dummyClients.length).toFixed(2);
  });
</script>

<div class="columns">
  <div class="column is-2">
    <article class={`
      message
      ${average < 7 ? "is-warning" : ""}
      ${average > 8 ? "is-primary" : ""}
    `}>
      <div class="message-header">
        <p>Média no NPS</p>
      </div>
      <div class="message-body has-text-centered">
        {average}
      </div>
    </article>
  </div>
</div>

