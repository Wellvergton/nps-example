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
  
  let npsGrade = 10;
  let showAcknowledgmentModal = false;
  
  function setNpsGrade(value) {
    npsGrade = value;
  }
  
  function showModal() {
    showAcknowledgmentModal = true;
  }
  
  function hideModal() {
    showAcknowledgmentModal = false;
  }
  
  function send() {
    let endpoint = `https://intense-badlands-39093.herokuapp.com/nps/add?npsGrade=${npsGrade}&likedShippingValue=${questions[0].like}&likedPrice=${questions[1].like}&likedNavigation=${questions[2].like}&likedPayment=${questions[3].like}&likedDelivery=${questions[4].like}`;
    const xhttp = new XMLHttpRequest();
    
    xhttp.onreadystatechange = function() {
      if (this.readyState == 4 && this.status == 200) {
        showModal();
      }
    }
    
    xhttp.open("POST", endpoint, true);
    xhttp.send();
  }
</script>

<div class="is-flex is-flex-direction-row is-justify-content-center">
  <form on:submit|preventDefault={() => {}}>
    <Nps onSelect={setNpsGrade} />

    {#each questions as question}
      <Field data={question} />
    {/each}
    
    <div class="field">
      <div class="field-label"></div>
      <div class="field-body">
        <div class="field">
          <div class="control">
            <button class="button is-primary" on:click={send}>
              Enviar
            </button>
          </div>
        </div>
      </div>
    </div>
  </form>
</div>

<AcknowledgmentModal isActive={showAcknowledgmentModal} />

