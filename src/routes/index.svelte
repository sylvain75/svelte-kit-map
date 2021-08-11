<script lang="ts">
  let localCount = 0;
  let textValue = '';
  import SharedCount from '../components/SharedCount.svelte'
  const handleChange = (operation: 'add' | 'substract') => {
    localCount = operation === 'add' ? ++localCount : --localCount;
  }

  $: console.log('TEXT', textValue)
  $: console.log('COUNT', localCount)
</script>

<h1>Welcome Count</h1>
<button on:click={() => handleChange('substract')}>-</button>
<button on:click={() => handleChange('add')}>+</button>
<input type="text" bind:value={textValue} />
<div>-------</div>
<SharedCount count={localCount} />
