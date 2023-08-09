<script lang="ts">
  import type Soul from 'models/soul';

  export let souls: Soul[];
</script>

<div>
  {#each souls as soul, i}
    <div>{soul.name}</div>
  {/each}
</div>
