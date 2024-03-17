<script>
  export let type = 'primary';
</script>

<button class={type}>
  <slot />
</button>

<style>
  button {
    background: linear-gradient(rgba(255, 255, 255, 0.2), transparent);
    border-radius: 6px;
    color: white;
    filter: drop-shadow(1px 2px 3px rgba(97, 64, 239, 0.4));
    font-family: 'Space Grotesk';
    font-weight: 600;
    margin-top: 20px;
    padding: 8px 16px;
  }

  .primary {
    background-color: #6140ef;
    border: 2px solid #5738e1;
  }

  .primary:hover {
    background: linear-gradient(rgba(255, 255, 255, 0.2), transparent),
      linear-gradient(transparent, rgba(0, 0, 0, 0.1));
    background-color: #6140ef;
  }

  .primary:active {
    background: linear-gradient(rgba(255, 255, 255, 0.1), transparent),
      linear-gradient(transparent, rgba(0, 0, 0, 0.1));
    background-color: #6140ef;
    box-shadow: inset 0 2px 2px 0 rgba(0, 0, 0, 0.15);
    color: rgba(255, 255, 255, 0.9);
    padding-top: 9px;
    padding-bottom: 7px;
    filter: none;
  }
</style>
