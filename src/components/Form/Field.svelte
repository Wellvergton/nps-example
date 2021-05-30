<script>
  export let data;
</script>

<div class="field is-horizontal">
  <div class="field-label">
    <label class="label">{data.text}</label>
  </div>
  <div class="field-body">
    <div class="field">
      <div class="control">
        <label class="radio">
          <input type="radio" name={data.name} bind:group={data.like} value={true}>
          Gostei
        </label>
        <label class="radio">
          <input type="radio" name={data.name} bind:group={data.like} value={false}>
          Não gostei
        </label>
      </div>
    </div>
  </div>
</div>

