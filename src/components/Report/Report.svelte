<script>
  import { onMount } from "svelte";
  import Average from "./Average.svelte";
  import ReportTable from "./ReportTable.svelte";
  
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

<section>
  <Average assessments={assessments} />
  <ReportTable assessments={assessments} />
</section>

