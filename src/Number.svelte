<script>
  import { calculatorInput } from './store.js';

  export let number;

  function onClickNumber() {
    if ($calculatorInput === '0') {
      $calculatorInput = number;
    } else
      $calculatorInput = $calculatorInput + number;
  }
</script>

<button type='button' class='btn-number-item' on:click={onClickNumber}>
  {number}
</button>

<style type="text/scss">
  .btn-number-item {
    border: 1px solid #000;
    padding: 1rem;
    margin: 0;
    cursor: pointer;
    transition: all 0.2s;

    flex: 1 1 30%;

    &:active {
      transform: scale(0.99);
    }
  }
</style>