<script>
  import { calculatorInput } from './store.js';

  import Number from './Number.svelte';
  import CalculationFunction from './CalculationFunction.svelte';

  const numbers = [ '7', '8', '9', '4', '5', '6', '1', '2', '3', '0'];
</script>

<div class='calculator'>
  <h1>
    Calculator
  </h1>

  <input type='text' bind:value={$calculatorInput} class='input-view' />

  <div class='button-wrap'>
    <div class='number-wrap'>
      {#each numbers as number}
        <Number number={number} />
      {/each}
    </div>

    <div class='sign-wrap'>
      <CalculationFunction />
    </div>
  </div>
</div>

<style type="text/scss">
  .input-view {
    text-align: right;
  }

  .button-wrap {
    width: 100%;
    display: flex;
    gap: 0.5rem;
  }

  .number-wrap {
    flex: 1 1 55%;

    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .sign-wrap {
    flex: 1 1 26%;
  }
</style>