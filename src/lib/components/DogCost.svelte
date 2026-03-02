<script>
  const prices = {
    food: 339,
    veterinary: 367,
    toys: 79,
    grooming: 99,
    other: 28
  };

  let food = $state(false);
  let veterinary = $state(false);
  let toys = $state(false);
  let grooming = $state(false);
  let other = $state(false);

  let total = $derived(
    (food ? prices.food : 0) +
    (veterinary ? prices.veterinary : 0) +
    (toys ? prices.toys : 0) +
    (grooming ? prices.grooming : 0) +
    (other ? prices.other : 0)
  );
</script>

<div class="calculator">
  <h3>Households With Dogs Only</h3>

  <button class="service" onclick={() => food = !food}>
    <span class="indicator">{food ? '✓' : '○'}</span>
    <span class="name">Food</span>
    <span class="price">${prices.food}/year</span>
  </button>

  <button class="service" onclick={() => veterinary = !veterinary}>
    <span class="indicator">{veterinary ? '✓' : '○'}</span>
    <span class="name">Veterinary Care</span>
    <span class="price">${prices.veterinary}/year</span>
  </button>

  <button class="service" onclick={() => toys = !toys}>
    <span class="indicator">{toys ? '✓' : '○'}</span>
    <span class="name">Toys</span>
    <span class="price">${prices.toys}/year</span>
  </button>

  <button class="service" onclick={() => grooming = !grooming}>
    <span class="indicator">{grooming ? '✓' : '○'}</span>
    <span class="name">Grooming</span>
    <span class="price">${prices.grooming}/year</span>
  </button>

  <button class="service" onclick={() => other = !other}>
    <span class="indicator">{other ? '✓' : '○'}</span>
    <span class="name">Other</span>
    <span class="price">${prices.other}/year</span>
  </button>

  <div class="summary">
    <span class="summary-label">Yearly Total:</span>
    <span class="summary-amount">${total.toFixed(2)}</span>
  </div>
</div>

<style>
  .calculator {
    padding: 1.5rem;
    background: var(--color-light-gray);
    margin: 2rem 0;
    max-width: 400px;
  }

  h3 {
    margin: 0 0 1rem !important;
  }

  .service {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    padding: 0.75rem;
    border: none;
    border-bottom: 1px solid #ddd;
    background: transparent;
    cursor: pointer;
    width: 100%;
    text-align: left;
  }

  .indicator {
    font-size: 1.25rem;
  }

  .name {
    flex: 1;
    font-weight: bold;
  }

  .price {
    color: #666;
  }

  .summary {
    display: flex;
    justify-content: space-between;
    margin-top: 1rem;
    padding-top: 1rem;
    border-top: 2px solid var(--color-dark-gray);
  }

  .summary-label {
    font-size: 1.125rem;
  }

  .summary-amount {
    font-size: 1.125rem;
    font-weight: bold;
    color: var(--color-accent);
  }
</style>