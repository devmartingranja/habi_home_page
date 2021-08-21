<script>
  export let type='text';
  export let placeholder='';
  export let align='left';
</script>

<input type={type} placeholder={placeholder} style="--align: {align}">

<style type="text/scss">
  @import '../styles/vars';

  input {
    background: $scarp-gray-000;
    color: $scarp-gray-400;
    border: 1px solid $scarp-gray-200;
    border-radius: 8px;
    width: 100%;
    height: 60px;
    margin: 1px;
    text-align: var(--align);
  }
  input:hover { 
    background: $bright-turquoise-000;
    border: 2px solid $bright-turquoise-500;
    border-radius: 8px;
  } 
  input:focus{
    outline: none;
  }
</style>