<div class="card">
  <slot />
</div>

<style>
  .card {
    background: #14151d;
    border-radius: 6px;
    box-shadow:
      inset 0 1px 0 0 rgba(255, 255, 255, 0.03),
      inset 0 0 0 1px rgba(255, 255, 255, 0.03),
      0 0 0 1px rgba(0, 0, 0, 0.1),
      0 2px 2px 0 rgba(0, 0, 0, 0.1),
      0 4px 4px 0 rgba(0, 0, 0, 0.1),
      0 8px 8px 0 rgba(0, 0, 0, 0.1);
    padding: 30px;
  }
</style>
