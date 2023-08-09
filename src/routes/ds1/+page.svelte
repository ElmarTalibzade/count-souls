<script lang="ts">
  import Calculator from '../../components/common/calculator.svelte';
  import type Soul from 'models/soulDefinition';

  const souls: Soul[] = [
    { name: 'Soul of a Lost Undead', value: 200 },
    { name: 'Large Soul of a Lost Undead', value: 500 },
    { name: 'Soul of a Nameless Soldier', value: 800 },
    { name: 'Large Soul of a Nameless Soldier', value: 1000 },
    { name: 'Soul of a Proud Knight', value: 2000 },
    { name: 'Large Soul of a Proud Knight', value: 3000 },
    { name: 'Soul of a Brave Warrior', value: 5000 },
    { name: 'Large Soul of a Brave Warrior', value: 8000 },
    { name: 'Soul of a Hero', value: 10000 },
    { name: 'Soul of a Great Hero', value: 20000 },
  ];
</script>

<h1>Dark Souls 1 + Remastered</h1>

<Calculator soulDefinitions={souls} />
