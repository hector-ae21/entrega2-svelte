<script>
  // Reactive state: counter initialized at 0.
  let count = 0;
  // Reactive state: name initialized with "Svelte".
  let name = "Svelte";

  // Reactive declaration: automatically calculates double the counter when `count` changes.
  $: doubled = count * 2;

  // Reactive declaration: generates a greeting that automatically updates when `name` changes.
  $: greeting = `Hello, ${name}!`;

  // Function to increment the counter.
  function increment() {
    count++;
  }

  // Function that executes when typing in the text field, updating the name.
  function updateName(event) {
    name = event.target.value;
  }
</script>

<!-- Main HTML content of the component, with style applied directly. -->
<main>
  <h1>Reactive Declarations in Svelte</h1>

  <!-- Block to increment the counter and display its value and the doubled value. -->
  <div>
    <button on:click={increment}>Increment</button>
    <p>Count: {count}</p>
    <p>Doubled: {doubled}</p>
  </div>

  <!-- Block with an input to update the name and display a reactive greeting. -->
  <div>
    <input type="text" value={name} on:input={updateName}>
    <p>{greeting}</p>
  </div>
</main>

<!-- Local styles for the component. -->
<style>
  main {
    text-align: center;
    padding: 50px;
    font-family: 'Arial', sans-serif;
  }
  input, button {
    padding: 10px;
    margin-top: 10px;
  }
  p {
    color: #333;
  }
</style>
