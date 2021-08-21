<script>
  import { MENU_OPTIONS } from '../constants/catalogs';

  export let open = false
</script>

<aside class:open>
  <nav>
    {#each MENU_OPTIONS as menuOption}
		  <a class="block" href={menuOption.href}>
        {menuOption.label}
      </a>
    {/each}
  </nav>
</aside>

<style type="text/scss">
  @import '../styles/vars';

  aside {
    left: -100%;
    transition: left 0.3s ease-in-out;
    position: fixed;
    width: calc(100% - 170px);
    height: 100%;
    background-color: #6301CC;
    bottom: 0;
    opacity: 0.9;
  }

  nav {
    display: flex;
    flex-direction: column;
    font: 1.2rem $open-sans;
    color: $white;
    align-items: center;
    justify-content: center;
    height: 100%;
    gap: 2rem;
  }

  a {
    color: $white;
    text-decoration: none;
  }

  .open {
    left: 0
  }
</style>