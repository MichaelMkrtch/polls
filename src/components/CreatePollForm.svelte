<script>
  import { createEventDispatcher } from 'svelte';
  import Card from '../ui/Card.svelte';
  import Button from '../ui/Button.svelte';

  let dispatch = createEventDispatcher();
  let fields = { question: '', optionA: '', optionB: '' };
  let errors = { question: '', optionA: '', optionB: '' };
  let valid = false;

  function handleSubmit() {
    valid = true;

    if (fields.question.trim().length < 5) {
      valid = false;
      errors.question = 'Question must be at least 5 characters long.';
    } else {
      errors.question = '';
    }

    if (fields.optionA.trim().length < 1) {
      valid = false;
      errors.optionA = 'Option A must be at least 1 character long.';
    } else {
      errors.optionA = '';
    }

    if (fields.optionB.trim().length < 1) {
      valid = false;
      errors.optionB = 'Option B must be at least 1 character long.';
    } else {
      errors.optionB = '';
    }

    if (valid) {
      let poll = { ...fields, votesA: 0, votesB: 0, id: Math.random() };
      dispatch('add', poll);
    }
  }
</script>

<div class="card-container">
  <Card>
    <form on:submit|preventDefault={handleSubmit}>
      <div class="form-field">
        <label for="question">Poll Question</label>
        <input type="text" id="question" bind:value={fields.question} />
        <div class="error">{errors.question}</div>
      </div>

      <div class="form-field">
        <label for="option-a">Option A</label>
        <input type="text" id="option-a" bind:value={fields.optionA} />
        <div class="error">{errors.optionA}</div>
      </div>

      <div class="form-field">
        <label for="option-b">Option B</label>
        <input type="text" id="option-b" bind:value={fields.optionB} />
        <div class="error">{errors.optionB}</div>
      </div>

      <Button>Add Poll</Button>
    </form>
  </Card>
</div>

<style>
  .card-container {
    margin: 0 auto;
    width: fit-content;
  }

  form {
    margin: 0 auto;
    text-align: center;
    width: 400px;
  }

  .form-field {
    margin: 20px auto;
  }

  input {
    background-color: #1f212b;
    border: 2px solid #25272d;
    border-radius: 6px;
    box-sizing: border-box;
    box-shadow: inset 0 1px 2px 1px rgba(0, 0, 0, 0.1);
    caret-color: aliceblue;
    outline: none;
    padding: 8px;
    width: 100%;
  }

  label {
    display: block;
    margin: 10px auto;
    text-align: left;
  }

  .error {
    color: #eb2b51;
    font-size: 500;
    font-weight: bold;
    margin-top: 10px;
  }
</style>
