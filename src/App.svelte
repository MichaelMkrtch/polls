<script>
  import Header from './components/Header.svelte';
  import Footer from './components/Footer.svelte';
  import Tabs from './ui/Tabs.svelte';

  let items = ['Current Polls', 'Add New Poll'];
  let activeItem = 'Current Polls';

  function handleTabChange(event) {
    activeItem = event.detail;
  }
</script>

<Header />
<main>
  <Tabs {activeItem} {items} on:tabChange={handleTabChange} />
  {#if activeItem === 'Current Polls'}
    <p>Polls list component goes here</p>
  {:else if activeItem === 'Add New Poll'}
    <p>New poll form component goes here</p>
  {/if}
</main>
<Footer />

<style>
  main {
    margin: 40px auto;
    max-width: 960px;
  }
</style>
