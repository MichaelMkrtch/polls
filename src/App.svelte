<script>
  import Header from './components/Header.svelte';
  import Footer from './components/Footer.svelte';
  import PollList from './components/PollList.svelte';
  import CreatePollForm from './components/CreatePollForm.svelte';
  import Tabs from './ui/Tabs.svelte';

  let items = ['Current Polls', 'Add New Poll'];
  let activeItem = 'Current Polls';

  function handleTabChange(event) {
    activeItem = event.detail;
  }

  let polls = [
    {
      id: 1,
      question: 'Python or JavaScript?',
      optionA: 'Python',
      optionB: 'JavaScript',
      votesA: 9,
      votesB: 15,
    },
  ];

  function handleAddPoll(event) {
    const poll = event.detail;
    polls = [poll, ...polls];
    console.log(polls);
    activeItem = 'Current Polls';
  }
</script>

<Header />
<main>
  <Tabs {activeItem} {items} on:tabChange={handleTabChange} />
  {#if activeItem === 'Current Polls'}
    <PollList {polls} />
  {:else if activeItem === 'Add New Poll'}
    <CreatePollForm on:add={handleAddPoll} />
  {/if}
</main>
<Footer />

<style>
  main {
    margin: 40px auto;
    max-width: 960px;
  }
</style>
