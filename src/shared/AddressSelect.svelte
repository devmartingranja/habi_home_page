<script>
  import {onMount} from "svelte";
  import Input from './Input.svelte';
  import Select from './Select.svelte';
  import {ROAD_TYPES, PROPERTY_TYPE} from '../constants/catalogs'
  import {URL_GET_AVAILABLE_CITIES_LIST, API_KEY} from '../constants/routs'

  let citiesItems = []

  onMount(async () => {
    let data = {}
    try {
      const res = await fetch(URL_GET_AVAILABLE_CITIES_LIST, {
        headers: {'x-api-key': API_KEY}
      })
      data = await res.json()
    } catch (e) {
      console.error(e)
    } finally {
      citiesItems = data.result ?? []
    }
  });

</script>

<div class="address-grid">
    <Select label="Ciudad" items={citiesItems}/>
    <Select label="Tipo de vía" items={ROAD_TYPES}/>
    <div class="addres-num-box">
        <div class="input-number">
            <Input placeholder="00" align="center"/>
        </div>
        <div>#</div>
        <div class="input-number">
            <Input placeholder="00" align="center"/>
        </div>
        <div>-</div>
        <div class="input-number">
            <Input placeholder="00" align="center"/>
        </div>
    </div>
    <Select label="Tipo de inmueble" items={PROPERTY_TYPE}/>
</div>

<style type="text/scss">
  @import '../styles/vars';

  .address-grid {
    display: grid;
    grid-template-columns: auto auto 11rem auto;
    gap: 1rem;
    color: $scarp-gray-400;
    min-width: 11rem;
  }

  .addres-num-box {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .input-number {
    width: 3rem;
  }
</style>