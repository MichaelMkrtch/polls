<script>
  import Card from '../ui/Card.svelte';

  export let poll;

  $: totalVotes = poll.votesA + poll.votesB;
</script>

<Card>
  <div class="poll">
    <h3>{poll.question}</h3>
    <p>Total votes: {totalVotes}</p>
    <div class="answer">
      <div class="percent percent-a"></div>
      <span>{poll.optionA} ({poll.votesA})</span>
    </div>
    <div class="answer">
      <div class="percent percent-b"></div>
      <span>{poll.optionB} ({poll.votesB})</span>
    </div>
  </div>
</Card>

<style>
  h3 {
    margin: 0 auto;
  }

  p {
    color: #aaa;
    font-size: 14px;
    margin-bottom: 30px;
    margin-top: 6px;
  }

  .answer {
    background: #fafafa;
    cursor: pointer;
    margin: 10px auto;
    position: relative;
  }

  .answer:hover {
    mix-blend-mode: multiply;
  }

  span {
    display: inline-block;
    padding: 10px 20px;
  }
</style>
