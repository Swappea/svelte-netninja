<script>
  export let message = "default value";
  export let showModal = false;
  export let isPromo = false;
</script>

<style>
  .backdrop {
    height: 100%;
    width: 100%;
    position: fixed;
    background: rgba(0, 0, 0, 0.8);
  }
  .modal {
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    text-align: center;
    margin: 10% auto;
    background: #fff;
  }

  .promo .modal {
    background: crimson;
    color: #fff;
  }
</style>

{#if showModal}
  <div class="backdrop" class:promo={isPromo} on:click|self>
    <div class="modal">
      <p>{message}</p>
    </div>
  </div>
{/if}
