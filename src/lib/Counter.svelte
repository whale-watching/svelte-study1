<script lang="ts">
  let count: number = 0;
  const increment = () => {
    count += 1;
  };

  $: doubled = count * 2;

  $: if (count >= 4) {
		alert(`count is dangerously high!`);
		count = 3;
	}
</script>

<div>
  <button on:click={increment}>
    count is {count}
  </button>
  <p>Styled!</p>
  <p>{doubled}</p>
</div>

<style>
  p {
    color: purple;
    font-family: "Comic Sans MS", cursive;
    font-size: 4em;
  }
</style>
