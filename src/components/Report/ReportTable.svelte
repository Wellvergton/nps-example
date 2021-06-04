<script>
  import { onMount } from "svelte";
  import Row from "./Row.svelte";
  
  let assessments = [];
  
  onMount(() => {
    const endpoint = "https://intense-badlands-39093.herokuapp.com/nps/all";
    const xhttp = new XMLHttpRequest();
    
    xhttp.onreadystatechange = function() {
	    if (this.readyState == 4 && this.status == 200) {
		    assessments = JSON.parse(xhttp.responseText);
	    }
    }
    
    xhttp.open("GET", endpoint, true);
    xhttp.send();
  });
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
      {#each assessments as client}
        <Row data={client} />
      {/each}
    </tbody>
  </table>
</div>

