<script>
  export let isActive;
</script>

<div class={`modal ${isActive ? "is-active" : ""}`}>
  <div class="modal-background"></div>
  <div class="modal-content">
    <div class="notification is-primary">
      <a class="delete"  href="/"></a>
      Agradecemos a sua resposta.
    </div>
  </div>
</div>

