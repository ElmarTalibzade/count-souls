<script lang="ts">
  import Calculator from '../../components/common/calculator.svelte';
  import type Soul from 'models/soulDefinition';

  const souls: Soul[] = [
    { name: 'Coldblood Dew (1)', value: 350 },
    { name: 'Coldblood Dew (2)', value: 500 },
    { name: 'Coldblood Dew (3)', value: 1000 },
    { name: 'Thick Coldblood (4)', value: 1200 },
    { name: 'Thick Coldblood (5)', value: 1500 },
    { name: 'Thick Coldblood (6)', value: 1800 },
    { name: 'Frenzied Coldblood (7)', value: 2000 },
    { name: 'Frenzied Coldblood (8)', value: 3000 },
    { name: 'Frenzied Coldblood (9)', value: 5000 },
    { name: 'Kin Coldblood (10)', value: 8000 },
    { name: 'Kin Coldblood (11)', value: 10000 },
    { name: 'Kin Coldblood (12)', value: 20000 },
    { name: 'Great One Coldblood', value: 40000 },
    { name: 'Old Great One Coldblood', value: 50000 },
  ];
</script>

<svelte:head>
  <title>Bloodborne</title>
</svelte:head>

<Calculator soulDefinitions={souls} />
