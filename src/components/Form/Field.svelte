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
          <input
            type="radio"
            name={data.name}
            bind:group={data.like}
            value={true}
          >
          <i
            class={`mx-4 my-3 fa fa-2x fa-thumbs-up ${data.like ? "has-text-info" : ""}`}
          >
          </i>
        </label>
        <label class="radio">
          <input
            type="radio"
            name={data.name}
            bind:group={data.like}
            value={false}
          >
          <i
            class={`mx-1 my-3 fa fa-2x fa-thumbs-down ${!data.like ? "has-text-danger" : ""}`}
          >
          </i>
        </label>
      </div>
    </div>
  </div>
</div>

<style>
  [type=radio] { 
    position: absolute;
    opacity: 0;
    width: 0;
    height: 0;
  }
</style>

