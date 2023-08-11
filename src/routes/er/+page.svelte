<script lang="ts">
  import Calculator from '../../components/common/calculator.svelte';
  import type Soul from 'models/soulDefinition';

  const souls: Soul[] = [
    { name: 'Golden Rune [1]', value: 200 },
    { name: 'Golden Rune [2]', value: 400 },
    { name: 'Golden Rune [3]', value: 800 },
    { name: 'Golden Rune [4]', value: 1200 },
    { name: 'Golden Rune [5]', value: 1600 },
    { name: 'Golden Rune [6]', value: 2000 },
    { name: 'Golden Rune [7]', value: 2500 },
    { name: 'Golden Rune [8]', value: 3000 },
    { name: 'Golden Rune [9]', value: 3800 },
    { name: 'Golden Rune [10]', value: 5000 },
    { name: 'Golden Rune [11]', value: 62500 },
    { name: 'Golden Rune [12]', value: 7500 },
    { name: 'Golden Rune [13]', value: 10000 },
    { name: "Numen's Rune", value: 12500 },
    { name: "Hero's Rune [1]", value: 15000 },
    { name: "Hero's Rune [2]", value: 20000 },
    { name: "Hero's Rune [3]", value: 25000 },
    { name: "Hero's Rune [4]", value: 30000 },
    { name: "Hero's Rune [5]", value: 35000 },
    { name: "Lord's Rune", value: 50000 },
  ];
</script>

<svelte:head>
  <title>Dark Souls 3</title>
</svelte:head>

<Calculator soulDefinitions={souls} />
