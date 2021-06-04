<script>
  import Row from "./Row.svelte";
  
  export let assessments;
</script>

<div class="table-container">
  <table class="table is-striped is-hoverable">
    <thead>
      <tr>
        <th>Client</th>
        <th>Nota do NPS</th>
        <th>Classificação<br>(Detrator, Neutro, Promotor)</th>
        <th>Valor do frete<br>(Curtiu / Não curtiu)</th>
        <th>Preço do produto<br>(Curtiu / Não curtiu)</th>
        <th>Navegação do site<br>(Curtiu / Não curtiu)</th>
        <th>Pagamento<br>(Curtiu / Não curtiu)</th>
        <th>Entrega<br>(Curtiu / Não curtiu)</th>
      </tr>
    </thead>
    <tbody>
      {#each assessments as assessment}
        <Row data={assessment} />
      {/each}
    </tbody>
  </table>
</div>

