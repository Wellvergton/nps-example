<script>
  export let onSelectScreen;
</script>

<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a class="navbar-item">
      <img
        src="https://fcxlabs.ferreiracosta.com/wp-content/uploads/2021/02/Logo-Labs.svg"
        width="112"
        height="28"
      >
    </a>

    <a
      role="button"
      class="navbar-burger"
      aria-label="menu"
      aria-expanded="false"
      data-target="navbarBasicExample"
    >
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </a>
  </div>

  <div id="navbarBasicExample" class="navbar-menu">
    <div class="navbar-start">
      <a class="navbar-item" on:click={() => onSelectScreen("nps")}>
        NPS
      </a>

      <a class="navbar-item" on:click={() => onSelectScreen("report")}>
        Relatório
      </a>
    </div>

    <div class="navbar-end">
      <div class="navbar-item">
        <div class="buttons">
          <a class="button is-primary">
            <strong>Sign up</strong>
          </a>
          <a class="button is-light">
            Log in
          </a>
        </div>
      </div>
    </div>
  </div>
</nav>
