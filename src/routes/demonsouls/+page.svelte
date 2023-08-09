<script lang="ts">
  import Calculator from '../../components/common/calculator.svelte';
  import type Soul from 'models/soulDefinition';

  const souls: Soul[] = [
    { name: 'Unknown Warrior Soul', value: 200 },
    { name: 'Unknown Hero Soul', value: 400 },
    { name: 'Renowned Warrior Soul', value: 800 },
  ];
</script>

<h1>Demon Souls + Remake</h1>

<Calculator soulDefinitions={souls} />
