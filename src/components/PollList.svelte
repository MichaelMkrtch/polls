<script>
  import PollDetails from './PollDetails.svelte';

  export let polls = [];
</script>

<div class="poll-list">
  {#each polls as poll (poll.id)}
    <div>
      <PollDetails {poll} />
    </div>
  {/each}
</div>

<style>
  .poll-list {
    display: grid;
    grid-gap: 20px;
    grid-template-columns: 1fr 1fr;
  }
</style>
