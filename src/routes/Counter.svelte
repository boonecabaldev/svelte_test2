<script>
  let count = 0;
  const increment = () => {
    return count += 1;
  }
</script>

<button on:click={increment}>
  count is {count}
</button>