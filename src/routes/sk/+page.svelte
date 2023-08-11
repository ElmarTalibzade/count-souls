<script lang="ts">
  import Calculator from '../../components/common/calculator.svelte';
  import type Soul from 'models/soulDefinition';

  const souls: Soul[] = [
    { name: 'Light Coin Purse', value: 100 },
    { name: 'Heavy Coin Purse', value: 500 },
    { name: 'Bulging Coin Purse', value: 1000 },
  ];
</script>

<Calculator heading="Sekiro" soulDefinitions={souls} />
