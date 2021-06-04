<script>
  import NpsOptions from "./NpsOptions/NpsOptions.svelte";
  import NpsOptionsMobile from "./NpsOptionsMobile/NpsOptionsMobile.svelte";
  
  export let onSelect;

  let values = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
  let selected = 10;
</script>

<div class="field">
  <p class="label">
    Qual a probabilidade de recomendar esta empresa a um amigo ou colega?
  </p>
  <NpsOptions values={values} selected={selected} onSelect={onSelect} />
  <NpsOptionsMobile values={values} selected={selected} onSelect={onSelect} />
</div>

