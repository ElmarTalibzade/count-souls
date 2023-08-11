<script lang="ts">
  import '../app.css';
  import Navbar from '../components/common/navbar.svelte';
</script>

<Navbar />
<div class="max-w-8x1 mx-auto md:px-96">
  <slot />
</div>
