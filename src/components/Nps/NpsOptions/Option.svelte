<script>
  export let value;
  export let isSelected;
  export let onClick;
</script>

<p class="control">
  <button
    class={`button ${isSelected ? "is-primary" : "is-outlined is-primary"}`}
    on:click={onClick}
  >
    {value}
  </button>
</p>

