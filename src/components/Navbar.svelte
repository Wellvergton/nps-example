<script>
  export let onSelectScreen;
  
  document.addEventListener('DOMContentLoaded', () => {
    const navbarBurgers = Array.prototype.slice.call(
      document.querySelectorAll('.navbar-burger'
    ), 0);

    if (navbarBurgers.length > 0) {
      navbarBurgers.forEach( el => {
        el.addEventListener('click', () => {
          const target = el.dataset.target;
          const burgerTarget = document.getElementById(target);
          el.classList.toggle('is-active');
          burgerTarget.classList.toggle('is-active');
        });
      });
    }
  });
</script>

<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
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

