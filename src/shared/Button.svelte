<script>
  export let label="";
</script>

<button>
  {label}
</button>

<style type="text/scss">
  @import '../styles/vars';

  button {
    background: $electric-purple-500;
    color: $white;
    font: 1rem $mulish;
    border-radius: 24px;
    border: 0;
    padding: 1rem 2rem;
    cursor: pointer;
  }

  @media only screen and (max-width: $mobile-max-width) {
    button {
      width: 100%;
    }
  }
</style>
