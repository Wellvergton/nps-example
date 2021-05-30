<script>
  import Option from "./Option.svelte";
  
  export let values;
  export let selected;
  export let onSelect;
</script>

<div class="field has-addons is-hidden-mobile">
  {#each values as value}
    <Option
      value={value}
      isSelected={value === selected}
      onClick={() => onSelect(value)}
    />
  {/each}
</div>

