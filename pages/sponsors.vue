<template>
  <div id="home-page" class="page-wrapper content-page">
    <site-hero
      title="Sponsors"
      subtitle=""
      image="/uploads/wita-pic-2.png"
    ></site-hero>
    <main-section theme="one-column">
      <template v-slot:default>
        <section class="content">
          <h1>We love our Sponsors!</h1>
          <p>
            <strong>Women in Tech Allies</strong> could not do what we do
            without the consistent support of our amazing sponsors. We have
            <a href="https://www.patreon.com/WomenInTechAllies">
              <span class="links">
                Patreon
              </span>
            </a>
            sponsors that support us and help "keep the doors open". They help
            offset some of the costs for tools and tech to keep this group
            active and growing.
          </p>
        </section>
      </template>
      <template v-slot:sidebar>
        Nothing here
      </template>
    </main-section>
    <news-letter-form-modal />
  </div>
</template>

<script>
import { mapState } from 'vuex'
import { setPageData } from '../helper'
import NewsLetterFormModal from '~/components/NewsLetterFormModal'

export default {
  name: 'HomePage',
  head() {
    return {
      title: `Home | ${this.$siteConfig.siteName}`
    }
  },
  components: {
    NewsLetterFormModal
  },
  computed: {
    ...mapState(['title', 'subtitle', 'featureImage'])
  },
  fetch({ store, params }) {
    setPageData(store, { slug: 'home' })
  }
}
</script>

<style>
.home-page .under-subtitle {
  border-top: none;
}
.links {
  color: #2de1fc;
  font-size: 1.3 rem;
  font-weight: bold;
}
</style>
