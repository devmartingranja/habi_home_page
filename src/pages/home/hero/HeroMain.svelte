<script>
  import AddressSelect from '../../../shared/AddressSelect.svelte';
  import Button from '../../../shared/Button.svelte';
  import Input from '../../../shared/Input.svelte';
</script>

<div class="hero-image-grid">
    <div class="message">
        <h1>
            Compramos tu casa en <br>
            <span class="color-primary">10 días*</span>
            <div class="underline"></div>
        </h1>
        <p>
            Ahórrate intermediarios, múltiples visitas y estrés, <b>recibe una oferta en tan solo minutos, rápido y
            totalmente gratis.</b>
        </p>
    </div>
    <div class="addres-select-desktop">
        <AddressSelect/>
    </div>
    <div class="addres-select-mobile">
        <Input placeholder="Escribe la dirección de tu inmueble"/>
    </div>
    <div>
        <Button label="Solicita tu oferta gratis"/>
    </div>
</div>

<style type="text/scss">
  @import '../../../styles/vars';

  h1 {
    font: 52px $mulish;
    font-weight: 800;
    line-height: 4rem;
    margin: 0;
  }

  p {
    font: 1.2rem $open-sans;
    font-style: normal;
    font-weight: normal;
    line-height: 2rem;
    color: $scarp-gray-700;
    margin: 0;
  }

  .hero-image-grid {
    display: flex;
    flex-direction: column;
    gap: 35px;
    justify-content: center;
  }

  .message {
    display: flex;
    flex-direction: column;
    gap: 35px;
    justify-content: center;
    max-width: 600px;
  }

  .underline {
    background: $electric-purple-500;
    border-radius: 3px;
    opacity: 0.25;
    width: 203px;
    height: 8px;
  }

  .addres-select-mobile {
    display: none;
  }

  @media only screen and (min-width: $tablet-min-width) and (max-width: $tablet-max-width) {
    h1 {
      font: 3rem $mulish;
      font-weight: 800;
    }
    .addres-select-desktop {
      display: none;
    }
    .addres-select-mobile {
      display: initial;
    }
  }

  @media only screen and (max-width: $mobile-max-width) {
    h1 {
      font: 2.3rem $mulish;
      font-weight: 800;
    }
    .addres-select-desktop {
      display: none;
    }
    .addres-select-mobile {
      display: initial;
    }
    .underline {
      width: 150px;
    }
  }


</style>