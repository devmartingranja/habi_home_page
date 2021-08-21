<script>
  import LazyLoad from '@dimfeld/svelte-lazyload'
  export let newItem = {}
</script>

<div class="new">
    <a href={newItem.data_item.url} class="new-link">
        <LazyLoad>
            <img src={newItem.image_desktop[0]?.url} class="lazyload" alt={newItem.title} width="196px" height="24px">
        </LazyLoad>
        <p>{newItem.description}</p>
    </a>
</div>

<style type="text/scss">

    .new {
        max-width: 196px;
        min-width: 196px;
        margin-right: 40px;
    }

    a {
        text-decoration: none;
    }

    .new a img {
        max-height: 24px;
    }

    p {
        font-family: "Open Sans",serif;
        font-style: normal;
        font-weight: normal;
        font-size: 15px;
        line-height: 14px;
        color: rgb(109, 105, 112);
    }
</style>