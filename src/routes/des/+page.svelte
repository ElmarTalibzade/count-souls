<script lang="ts">
  import Calculator from '../../components/common/calculator.svelte';
  import type Soul from 'models/soulDefinition';

  const souls: Soul[] = [
    { name: 'Unknown Warrior Soul', value: 200 },
    { name: 'Unknown Hero Soul', value: 400 },
    { name: 'Renowned Warrior Soul', value: 800 },
    { name: 'Renowned Hero Soul', value: 1000 },
    { name: 'Storied Warrior Soul', value: 2000 },
    { name: 'Storied Hero Soul', value: 4000 },
    { name: 'Legendary Warrior Soul', value: 8000 },
    { name: 'Legendary Hero Soul', value: 10000 },
  ];
</script>

<Calculator heading="Demon Souls + Remake" soulDefinitions={souls} />
