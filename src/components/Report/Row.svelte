<script>
  import LikeOrDeslikeCell from "./LikeOrDeslikeCell.svelte";
  import ClassificationCell from "./ClassificationCell.svelte";

  export let data;
  
  function setColorByGrade(grade) {
    if (grade > 8) {
      return "has-background-primary";
    }
    
    if (grade < 7) {
      return "has-background-warning";
    }
  }
</script>


<tr class={setColorByGrade(data.npsGrade)}>
  <td>{data.id}</td>
  <td>{data.npsGrade}</td>
  <ClassificationCell npsGrade={data.npsGrade} />
  <LikeOrDeslikeCell isLike={data.likedShippingValue} />
  <LikeOrDeslikeCell isLike={data.likedPrice} />
  <LikeOrDeslikeCell isLike={data.likedNavigation} />
  <LikeOrDeslikeCell isLike={data.likedPayment} />
  <LikeOrDeslikeCell isLike={data.likedDelivery} />
</tr>

