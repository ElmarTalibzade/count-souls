<script lang="ts">
  import type SoulCalculation from 'models/soulCalculation';
  import type SoulDefinition from 'models/soulDefinition';

  const soulSummaryHeight = 32;

  export let soulDefinitions: SoulDefinition[];

  let soulCalculations: SoulCalculation[];
  reset();

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

  function reset() {
    soulCalculations = soulDefinitions.map((definition) => ({
      definition: definition,
      quantity: 0,
    }));
  }
</script>

<div class="grid grid-cols-2 gap-1 p-1 mb-{soulSummaryHeight}">
  {#each soulCalculations as soul, i}
    <div class="flex flex-col justify-between border border-solid rounded-lg p-3">
      <div>
        <div class="mb-1 text-center text-base">{soul.definition.name}</div>
        <div class="mb-1 text-center text-xs">{soul.definition.value.toLocaleString()}</div>
      </div>
      <div class="flex items-center">
        <button
          on:click={() => decrement(i)}
          class="bg-orange-dark rounded-lg p-4 shadow-md text-base w-20">-</button
        >
        <div class="text-base w-20 text-center">{soul.quantity.toLocaleString()}</div>
        <button
          on:click={() => increment(i)}
          class="bg-orange-dark rounded-lg p-4 shadow-md text-base w-20">+</button
        >
      </div>
    </div>
  {/each}
</div>

<div
  class="h-{soulSummaryHeight} w-full bg-white inset-x-0 bottom-0 fixed border p-1 flex flex-col justify-center items-center"
>
  <p class="text-xl uppercase">Total</p>
  <div class="text-7xl">
    {soulsTotal.toLocaleString()}
  </div>
</div>
