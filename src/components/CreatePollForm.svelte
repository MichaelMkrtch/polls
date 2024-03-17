<script>
  import Button from '../ui/Button.svelte';

  let fields = { question: '', optionA: '', optionB: '' };

  function handleSubmit() {
    console.log(fields);
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <div class="form-field">
    <label for="question">Poll Question</label>
    <input type="text" id="question" bind:value={fields.question} />
  </div>

  <div class="form-field">
    <label for="option-a">Option A</label>
    <input type="text" id="option-a" bind:value={fields.optionA} />
  </div>

  <div class="form-field">
    <label for="option-b">Option B</label>
    <input type="text" id="option-b" bind:value={fields.optionB} />
  </div>

  <Button>Add Poll</Button>
</form>

<style>
  form {
    margin: 0 auto;
    text-align: center;
    width: 400px;
  }

  .form-field {
    margin: 20px auto;
  }

  input {
    border: 2px solid #eef0f3;
    border-radius: 6px;
    box-sizing: border-box;
    padding: 8px;
    width: 100%;
  }

  label {
    color: #555;
    display: block;
    margin: 10px auto;
    text-align: left;
  }
</style>
