<script lang="ts">
  import type SoulCalculation from 'models/soulCalculation';
  import type SoulDefinition from 'models/soulDefinition';

  export let soulDefinitions: SoulDefinition[];

  let soulCalculations: SoulCalculation[] = soulDefinitions.map((definition) => ({
    definition: definition,
    quantity: 0,
  }));

  $: soulsTotal = soulCalculations.reduce<number>((prev, soul) => {
    return prev + soul.definition.value * soul.quantity;
  }, 0);

  function increment(index: number) {
    const newQuantity = soulCalculations[index].quantity + 1;
    setQuantity(index, newQuantity);
  }

  function decrement(index: number) {
    const newQuantity = soulCalculations[index].quantity - 1;
    setQuantity(index, newQuantity);
  }

  function setQuantity(index: number, newQuantity: number) {
    soulCalculations[index].quantity = Math.max(0, newQuantity);
    soulCalculations = soulCalculations;
  }
</script>

<div class="flex flex-row flex-wrap">
  {#each soulCalculations as soul, i}
    <div class="grow border border-solid rounded-lg p-3 m-1">
      <div class="mb-1 text-center text-base">{soul.definition.name}</div>
      <div class="mb-1 text-center text-xs">{soul.definition.value}</div>
      <div class="flex items-center justify-between">
        <button
          on:click={() => decrement(i)}
          class="bg-orange-dark rounded-lg p-4 shadow-md text-base">-</button
        >
        <div class="text-base">{soul.quantity}</div>
        <button
          on:click={() => increment(i)}
          class="bg-orange-dark rounded-lg p-4 shadow-md text-base">+</button
        >
      </div>
    </div>
  {/each}
</div>

<div>
  Total: {soulsTotal}
</div>
