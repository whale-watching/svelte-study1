<script lang="ts">
  import Counter from "./lib/Counter.svelte";
  import Nested from "./lib/Nested.svelte";
  import Await from "./lib/Await.svelte";
  import Keyboard from "./lib/Keyboard.svelte";
  import Time from "./lib/Time.svelte";
  import Transition from "./lib/Transition.svelte";

  let pin;
  $: view = pin ? pin.replace(/\d(?!$)/g, "•") : "enter your pin";

  function handleSubmit() {
    alert(`submitted ${pin}`);
  }
</script>

<main>
  <div class="card">
    <Counter />
    <Nested answer={27} />
    <Transition />
    <Await />
    <h2 style="color: {pin ? '#333' : '#f00'}">{view}</h2>
    <Keyboard bind:value={pin} on:submit={handleSubmit} />
    <Time />
  </div>
</main>

<style>
</style>
