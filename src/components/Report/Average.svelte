<script>
  import { beforeUpdate } from "svelte";
  
  export let assessments;
  let average;
  
  beforeUpdate(() => {
    let total = 0;
    
    assessments.forEach((assessment) => total += assessment.npsGrade);
    
    average = assessments.length ? (total / assessments.length).toFixed(2) : "";
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

