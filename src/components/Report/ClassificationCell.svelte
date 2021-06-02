<script>
  export let npsGrade;
  
  function setClassification(grade) {
    if (grade > 8) {
      return "Promotor";
    }
    
    if (grade > 6) {
      return "Neutro";
    }
    
    return "Detrator";
  }
</script>

<td>
  {setClassification(npsGrade)}
</td>
