<script lang="ts">
  import type SoulCalculation from 'models/soulCalculation';
  import type SoulDefinition from 'models/soulDefinition';

  export let soulDefinitions: SoulDefinition[];
  export let heading: string;

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

<svelte:head>
  <title>{heading}</title>
</svelte:head>

<p class="text-bold text-center text-base">{heading}</p>

<div class="mb-32 grid grid-cols-2 gap-1 p-1">
  {#each soulCalculations as soul, i}
    <div class="flex flex-col justify-between rounded-lg border border-solid p-3">
      <div>
        <div class="mb-1 text-center text-base">{soul.definition.name}</div>
        <div class="mb-1 text-center text-xs">{soul.definition.value.toLocaleString()}</div>
      </div>
      <div class="flex items-center">
        <button
          on:click={() => decrement(i)}
          class="bg-orange-dark w-20 rounded-lg p-4 text-base shadow-md">-</button
        >
        <div class="w-20 text-center text-base">{soul.quantity.toLocaleString()}</div>
        <button
          on:click={() => increment(i)}
          class="bg-orange-dark w-20 rounded-lg p-4 text-base shadow-md">+</button
        >
      </div>
    </div>
  {/each}
</div>

<div
  class="fixed inset-x-0 bottom-0 flex h-32 w-full flex-col items-center justify-center border bg-white p-1"
>
  <p class="text-xl uppercase">Total</p>
  <div class="text-7xl">
    {soulsTotal.toLocaleString()}
  </div>
</div>
