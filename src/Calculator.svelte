<script>
  export let title = "";

  let allCalculation = "";
  let displayValue = "";
  let totalized = false;

  function calculate() {
    const infoToCalculate = allCalculation.split(" ");

    let total = 0;

    for (let i = 0; i < infoToCalculate.length; i++) {
      const operator = infoToCalculate[i - 1] ? infoToCalculate[i - 1] : null;
      const value = infoToCalculate[i];

      if (i === 0) {
        total = Number(value);
      }

      switch (operator) {
        case "+":
          total = total + Number(value);
          break;
        case "-":
          total = total - Number(value);
          break;
        case "x":
          total = total * Number(value);
          break;
        case "÷":
          total = total / Number(value);
          break;

        default:
          break;
      }
    }

    return total;
  }

  function handleEqualClick(event) {
    if (totalized) {
      return;
    }

    handleClickButton(event);

    totalized = true;

    const result = calculate();

    allCalculation += result;

    displayValue = result;
  }

  function handleClearClick() {
    allCalculation = "";
    displayValue = "";
    totalized = false;
  }

  function handleBackspaceClick() {
    displayValue = `${displayValue}`.slice(0, -1);
  }

  function handleClickButton(event) {
    const value = event.target.innerText;

    const decimalSeparator = value === ",";
    const isOperador = isNaN(value) && !decimalSeparator;

    if (isOperador) {
      const operator = value;

      if (totalized) {
        allCalculation = `${displayValue} ${operator} `;
        displayValue = "";
        totalized = false;
      } else {
      allCalculation += `${displayValue} ${operator} `;
      displayValue = "";
      }

      return;
    }
    
    const sepatator = displayValue ? "." : "0.";

    if (totalized) {
      totalized = false
      displayValue = decimalSeparator ? sepatator : value;
    } else {
      displayValue += decimalSeparator ? sepatator : value;
    }
  }
</script>

<div>
  <p class="text-gray-100 text-2xl text-center mb-10">{title}</p>

  <div class="flex-col p-3 bg-gray-100 max-w-xs rounded">
    <div class="flex flex-col mb-10">
      <textarea 
        class="bg-gray-300 border-none resize-none text-sm rounded mb-1 h-20 p-2 m-2"
      >{allCalculation}</textarea>
      
      <p class="overflow-hidden bg-gray-300 text-gray-800 font-bold m-2 p-2 text-2xl text-right h-12 rounded">
        {displayValue}
      </p>      
    </div>

    <div class="inline-grid grid-cols-2 grid-rows-1 h-full w-full">
      <button class="text-sm text-gray-500 m-4" on:click={handleClearClick}>
        clear all
      </button>

      {#if !totalized}
      <button
        class="flex items-center justify-end border-none pr-1"
        on:click={handleBackspaceClick}
      >
        <svg
          class="h-8 w-8 text-gray-500 hover:text-red-500"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          stroke-width="1"
          stroke="currentColor"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path stroke="none" d="M0 0h24v24H0z" />
          <path
            d="M20 6a1 1 0 0 1 1 1v10a1 1 0 0 1 -1 1h-11l-5 -5a1.5 1.5 0 0 1 0 -2l5 -5Z"
          /> <path d="M12 10l4 4m0 -4l-4 4" /></svg
        >
      </button>
      {/if}
    </div>

    <div class="flex flex-1 flex-row">
      <div class="flex-initial w-64 p-1">
        <div class="inline-grid grid-cols-3 grid-rows-4 gap-4 h-full w-full">
          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >7</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >8</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >9</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >6</button>
          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >5</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >4</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >3</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >2</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >1</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >,</button>

          <button
            on:click={handleClickButton}
            class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded"
          >0</button>

          <button
            on:click={handleEqualClick}
            class="bg-yellow-600 hover:bg-yellow-700 text-white font-bold py-2 px-4 rounded-full"
          >=</button>
        </div>
      </div>

      <div class="flex-initial w-16 p-1">
        <div class="grid grid-cols-1 grid-rows-4 gap-4">
          <button
            on:click={handleClickButton}
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
          >÷</button>

          <button
            on:click={handleClickButton}
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
          >x</button>
          
          <button
            on:click={handleClickButton}
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
          >+</button>

          <button
            on:click={handleClickButton}
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
          >-</button>
        </div>
      </div>
    </div>
  </div>
</div>
