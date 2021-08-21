<script>
  export let open = false
</script>

<div class="menu-button" on:click={() => open = !open}>
  <div>
    Menú
  </div>
  <div class={open? 'btn open': 'btn'}>
    <svg width=24 height=19>
     <line id="top" x1=0 y1=2 x2=24 y2=2/>
     <line id="middle" x1=0 y1=8 x2=24 y2=8/>
     <line id="bottom" x1=0 y1=14 x2=24 y2=14/>
    </svg>
  </div>
</div>

<style type="text/scss">
  @import '../styles/vars';

  svg {
    min-height: 20px;
    transition: transform 0.3s ease-in-out;
  }
  
  svg line {
    stroke: currentColor;
    stroke-width: 2;
    transition: transform 0.3s ease-in-out
  }
  
  .btn {
    height: 16px;
  }

  .open svg {
    transform: scale(0.8)
  }
  
  .open #top {
    transform: translate(7px, -2px) rotate(45deg)
  }
  
  .open #middle {
    opacity: 0;
  }
  
  .open #bottom {
    transform: translate(-4px, 6px) rotate(-45deg)
  }

  .menu-button {
    font: 0.9rem $mulish;
    font-weight: 800;
    border: 1px solid $scarp-gray-100;
    border-radius: 12px;
    display: flex;
    cursor: pointer;
    padding: 8px 12px;
    align-items: center;
    gap: 0.8rem;
  }
</style>