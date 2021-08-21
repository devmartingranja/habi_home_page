<script>
  import HeroImage from "./HeroImage.svelte";
  import HeroMain from "./HeroMain.svelte";
</script>

<div class="hero-grid ">
  <div class="main">
    <HeroMain />
  </div>
  <div class="image">
    <HeroImage />
  </div>
</div>

<style type="text/scss">
  @import "../../../styles/vars";

  .hero-grid {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-gap: 2rem;
  }
  .main {
    grid-column: 1 / 8;
  }
  .image {
    grid-column: 8 / 13;
  }

  @media only screen and (min-width: $tablet-min-width) and (max-width: $tablet-max-width) {
    .hero-grid {
      grid-template-columns: repeat(8, 1fr);
    }
    .main {
      grid-column: 1 / 5;
    }
    .image {
      grid-column: 5 / 9;
    }
  }

  @media only screen and (max-width: $mobile-max-width) {
    .hero-grid {
      grid-template-columns: 4fr;
    }
    .main {
      grid-column: 1 / 5;
      order: 2;
    }
    .image {
      grid-column: 1 / 5;
      order: 1;
    }
  }
</style>
