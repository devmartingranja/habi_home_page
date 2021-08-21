<script>
  import {onMount} from 'svelte'
  import Starts from '../garage/Starts.svelte'
  import NewsItem from './NewsItem.svelte'
  import {URL_STRAPI, URL_STRAPI_HTTP2} from '../../../constants/routs'

  let newsItems = []

  onMount(async () => {
    let data = []
    try {
      const res = await fetch(URL_STRAPI)
      data = await res.json()
    } catch (e) {
      console.error(e)
    } finally {
      let arrayHomeNews = (data.filter(e => e.component_name === 'home_news'))[0] ?? []
      newsItems = arrayHomeNews.items ?? []
      newsItems = newsItems.map(newItem => {
        newItem.image_desktop = newItem.image_desktop.map(img => ({
          ...img,
          url: `${URL_STRAPI_HTTP2}${(img.url.split('/').reverse())[0]}`
        }))
        return newItem
      })
    }
  })
</script>

<div class="news">
    <Starts/>
    <div class="news-container">
        <div class="news-body">
            {#each newsItems as newItem}
                <NewsItem {newItem}/>
            {:else }
                ...Loading
            {/each}
        </div>
    </div>
</div>

<style type="text/scss">

  .news {
    display: grid;
  }

  .news-container {
    overflow: auto;
    padding: 32px 16px;
    justify-content: center;
  }

  .news-body {
    height: auto;
    overflow-y: hidden;
    display: flex;
    width: 100%;
  }
</style>