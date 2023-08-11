<script lang="ts">
  import menu from '../../assets/icon_menu.svg';

  let menuOpen: boolean = false;

  function toggleMenu() {
    menuOpen = !menuOpen;
  }
</script>

<button
  on:click={toggleMenu}
  class="sticky left-0 top-0 flex h-14 w-full flex-row items-center border-b bg-white"
>
  <img class="mr-1 w-8 flex-none p-1" src={menu} alt="Menu" />
  <h1 class="select-none text-3xl font-bold">Count Souls</h1>
</button>

{#if menuOpen}
  <div class="items fixed z-40 mb-2 flex h-full w-full flex-col items-center bg-white p-2">
    <p class="text-x3 mb-3">Select a game</p>

    <div class="flex flex-col items-center space-y-3 text-2xl">
      <a href="/des">Demon Souls + Remake</a>
      <a href="/ds1">Dark Souls I + Remastered</a>
      <a href="/ds2">Dark Souls II</a>
      <a href="/ds3">Dark Souls III</a>
      <a href="/bb">Bloodborne</a>
      <a href="/er">Elden Ring</a>
    </div>

    <a class="m-10" href="https://ko-fi.com/C0C8O3SFV" target="_blank"
      ><img
        class="w-36 border-0"
        src="https://storage.ko-fi.com/cdn/kofi3.png?v=3"
        alt="Support me at ko-fi.com"
      /></a
    >
  </div>
{/if}
