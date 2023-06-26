<script>
  import { calculatorInput } from './store.js';

  function reset() {
    $calculatorInput = '0';
  }

  const calculationFunctions = ['+', '-', '*', '/'];

  function calculationFunction(_insert) {
    const lastValue = $calculatorInput[$calculatorInput.length - 1];
    // 초기 0 상태이거나, 같은 기호면 연산 삽입 하지 않음
    if ($calculatorInput !== 0 && !calculationFunctions.includes(lastValue))
      $calculatorInput = $calculatorInput + _insert;
  }


  function subtraction() {}
  function multiplication() {}
  function division() {}

  function sum() {
    const isInputNaN = Number.isNaN(Number($calculatorInput));

    if (isInputNaN) {
      const sumLists = $calculatorInput.split('+');
      console.log('sumLists', sumLists);
      $calculatorInput = sumLists.reduce((pre, cur) => {
        return Number(pre) + Number(cur);
      });
    }
  }

  // $calculatorInput = '
</script>

<button class='calculator-sign-item full' on:click={reset}>C</button>

<button class='calculator-sign-item' on:click={() => calculationFunction('+')}>+</button>
<button class='calculator-sign-item' on:click={() => calculationFunction('-')}>-</button>
<button class='calculator-sign-item' on:click={() => calculationFunction('*')}>*</button>
<button class='calculator-sign-item' on:click={() => calculationFunction('/')}>/</button>

<button class='calculator-sign-item full' on:click={sum}>=</button>


<style type="text/scss">
  .calculator-sign-item {
    padding: 1rem;
    border: 1px solid #000;
    cursor: pointer;
    flex: 1;

  &:active {
     transform: scale(0.99);
   }

  &.full {
     width: 100%;
   }
  }
</style>