<script>
  import LazyLoad from '@dimfeld/svelte-lazyload'
</script>

<div class="starts">
    <div class="news-stars">
        <div class="news-stars-star">
        </div>
        <div class="news-stars-star">
            <LazyLoad>
                <img src="/assets/images/start.svg" alt="start" width="18" height="17"/>
            </LazyLoad>
        </div>
        <div class="news-stars-star">
            <LazyLoad>
                <img src="/assets/images/start.svg" alt="start" width="18" height="17"/>
            </LazyLoad>
        </div>
        <div class="news-stars-star">
            <LazyLoad>
                <img src="/assets/images/start.svg" alt="start" width="18" height="17"/>
            </LazyLoad>
        </div>
        <div class="news-stars-star">
            <LazyLoad>
                <img src="/assets/images/start.svg" alt="start" width="18" height="17"/>
            </LazyLoad>
        </div>
    </div>
</div>

<style type="text/scss">

  .starts {
    width: 100%;
  }

  .news-stars {
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin: 16px 16px;
  }
</style>