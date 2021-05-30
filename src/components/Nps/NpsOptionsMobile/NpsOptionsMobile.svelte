<script>
  import Option from "./Option.svelte";

  export let values;
  export let selected;
  export let onSelect;
</script>

<div class="select is-primary is-hidden-tablet">
  <select bind:value={selected} on:blur={() => onSelect(selected)}>
    {#each values as value}
      <Option value={value} />
    {/each}
  </select>
</div>

