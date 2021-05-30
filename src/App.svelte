<script>
  import Form from "./components/Form/Form.svelte";
  import Navbar from "./components/Navbar.svelte";
  import Nps from "./components/Nps/Nps.svelte";
  import ReportTable from "./components/ReportTable/ReportTable.svelte";
  
  let selectedScreen = "nps";
  
  function selectScreen(screen) {
    selectedScreen = screen;
  }
</script>

<Navbar onSelectScreen={selectScreen} />
<main class="section">
  {#if selectedScreen === "nps"}
    <Form />
  {/if}
  
  {#if selectedScreen === "report"}
    <ReportTable />
  {/if}
</main>

