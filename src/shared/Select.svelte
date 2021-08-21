<script>  
  import Select from 'svelte-select';

  export let label;
  export let items=[];
  export let value=''

</script>

<div class="select-box">
  <span>
    {label}
  </span>
  <div class="themed">
    <Select {items} {value} placeholder="Seleccione" isClearable={false} showIndicator={true}/>
  </div>
</div>

<style type="text/scss">
  @import '../styles/vars';

  span {
    font: 0.8rem $open-sans;
    font-style: normal;
    font-weight: 600;
    line-height: 1rem;
    margin: 6px 0 0 8px;
    display: block;
    color: $scarp-gray-700;
  }
  .themed {
    --background: transparent;
    --border: 0px;
    --inputFontSize: 1rem;
    --inputPadding: 0 20px 6px 8px;
    --height: 38px;
  }
  .select-box {
    border-radius: 8px;
    background: $scarp-gray-000;
    border: 1px solid $scarp-gray-200;
    margin: 1px;
  }
  .select-box:hover {
    border-radius: 8px;
    background: $bright-turquoise-000;
    border: 2px solid $bright-turquoise-500;
    margin: 0;
  }
</style>