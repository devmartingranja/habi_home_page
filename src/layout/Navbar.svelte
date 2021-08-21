<script>
  import { MENU_OPTIONS } from '../constants/catalogs';
  import Hamburguer from './Hamburguer.svelte';

  export let sidebar = false
</script>

<div class="navbar-box">
  <div>
    <img src="/assets/images/habi-logo.svg" alt="Logo Habi" width="45px" height="43px" />
  </div>
  <div>
    <nav class="nav-desktop">
      {#each MENU_OPTIONS as menuOption}
        <a class="block" href={menuOption.href}>
          {menuOption.label}
        </a>
      {/each}
    </nav>
    <div class="nav-mobile">
      <Hamburguer bind:open={sidebar}/>
    </div>
  </div>
</div>

<style type="text/scss">
  @import '../styles/vars';

  a {
    font: 1rem $open-sans;
    font-style: normal;
    font-weight: 600;
    line-height: 28px;
    color: $scarp-gray-700;
  }

  a:hover {
    text-decoration: none;
  }

  .navbar-box {
    display: flex;
    justify-content: space-between;
    margin-bottom: 4rem;
  }

  .nav-desktop {
    display: flex;
    gap: 3.5rem;

  }

  .nav-mobile {
    display: none;
  }

  @media only screen and (max-width: $tablet-max-width) {
    .nav-desktop {
      display: none;
    }
    .nav-mobile {
      display: initial;
    }
  }

  @media only screen and (max-width: $mobile-max-width) {
    .navbar-box {
      margin-bottom: 18px;
    }
  }
</style>
