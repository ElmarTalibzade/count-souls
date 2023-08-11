<script lang="ts">
  import Calculator from '../../components/common/calculator.svelte';
  import type Soul from 'models/soulDefinition';

  const souls: Soul[] = [
    { name: 'Fading Soul', value: 50 },
    { name: 'Soul of a Deserted Corpse', value: 200 },
    { name: 'Large Soul of a Deserted Corpse', value: 400 },
    { name: 'Soul of an Unknown Traveler', value: 800 },
    { name: 'Large Soul of an Unknown Traveler', value: 800 },
    { name: 'Large Soul of an Unknown Traveler', value: 1000 },
    { name: 'Soul of a Nameless Soldier', value: 2000 },
    { name: 'Large Soul of a Nameless Soldier', value: 3000 },
    { name: 'Soul of a Weary Warrior', value: 5000 },
    { name: 'Large Soul of a Weary Warrior', value: 8000 },
    { name: 'Soul of a Crestfallen Knight', value: 10000 },
    { name: 'Large Soul of a Crestfallen Knight', value: 20000 },
    { name: 'Soul of a Proud Paladin', value: 500 },
    { name: 'Large Soul of a Proud Paladin', value: 1000 },
    { name: 'Soul of an Intrepid Hero', value: 2000 },
    { name: 'Large Soul of an Intrepid Hero', value: 2500 },
    { name: 'Soul of a Seasoned Warrior', value: 2000 },
    { name: 'Large Soul of a Seasoned Warrior', value: 7500 },
    { name: 'Soul of an Old Hand', value: 12500 },
    { name: 'Soul of a Venerable Old Hand', value: 20000 },
    { name: 'Soul of a Champion', value: 25000 },
    { name: 'Soul of a Great Champion', value: 50000 },
  ];
</script>

<Calculator heading="Dark Souls 3" soulDefinitions={souls} />
