<script>
  import AcknowledgmentModal from "./AcknowledgmentModal.svelte";
  import Nps from "../Nps/Nps.svelte";
  import Field from "./Field.svelte";
  
  const questions = [
    {
      name: "shipping-value",
      text: "Valor do frete",
      like: true,
    },
    {
      name: "price",
      text: "Preço do produto",
      like: true,
    },
    {
      name: "navigation",
      text: "Navegação no site",
      like: true,
    },
    {
      name: "payment",
      text: "Pagamento",
      like: true,
    },
    {
      name: "delivery",
      text: "Entrega",
      like: true,
    }
  ];
  
  let showAcknowledgmentModal = false;
  
  function showModal() {
    showAcknowledgmentModal = true;
  }
  
  function hideModal() {
    showAcknowledgmentModal = false;
  }
</script>

<form on:submit|preventDefault={() => {}}>
  <Nps />

  {#each questions as question}
    <Field data={question} />
  {/each}
  
  <div class="field">
    <div class="field-label"></div>
    <div class="field-body">
      <div class="field">
        <div class="control">
          <button class="button is-primary" on:click={showModal}>
            Enviar
          </button>
        </div>
      </div>
    </div>
  </div>
</form>

<AcknowledgmentModal isActive={showAcknowledgmentModal} onDismiss={hideModal} />

