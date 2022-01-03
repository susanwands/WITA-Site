<template>
  <div id="home-page" class="page-wrapper content-page">
    <site-hero :title="title" :subtitle="subtitle" :image="featureImage">
      <button
        v-if="$siteConfig.newsletter.on"
        class="button is-primary"
        @click="$eventBus.$emit('modal-triggered', 'newsletter-modal')"
      >
        Subscribe To Newsletter
      </button>
    </site-hero>
    <main-section theme="one-column">
      <template v-slot:default>
        <section class="content">
          <h1>What we're about</h1>
          <p>
            <strong>Women in Tech Allies</strong> is a group to advocate for
            women in tech careers through networking, tech talks, mentorship,
            etc. We look for opportunities to support our current peers in tech,
            women attempting to transition into tech from other backgrounds, as
            well as helping our youth grow into future tech leaders.
          </p>

          <p>
            Change comes from within. For the tech and dev community to become
            more inclusive and accessible for women and other underrepresented
            demographics, those already within the community must be part of
            that change.
          </p>

          <p>
            <strong>Women in Tech Allies</strong> is a space to apply your
            interests, expertise, experience, knowledge, support and
            encouragement to promote new tech talent. We encourage all genders,
            races and backgrounds to join our meetup and the tech community.
          </p>

          <p>
            Support us on
            <a href="https://www.patreon.com/WomenInTechAllies">
              <span class="links">
                Patreon
              </span>
            </a>
          </p>

          <p>
            Follow Us on
            <a href="https://twitter.com/WomenTechAllies">
              <span class="links">
                Twitter
              </span>
            </a>
          </p>

          <p>
            Connect on

            <a href="https://www.linkedin.com/company/women-in-tech-allies">
              <span class="links">
                LinkedIn
              </span>
            </a>
          </p>
          <p>
            Chat in the
            <a
              href="https://join.slack.com/t/womenintechallies/shared_invite/zt-3hwj28d1-vrqkscsAfmQrjdQzZhGHxQ"
            >
              <span class="links">
                Slack Group
              </span>
            </a>
          </p>
          <p>
            Find past event info on
            <a href="https://github.com/WomenInTechAllies">
              <span class="links">
                Github
              </span>
            </a>
          </p>
          <p>
            Join our next event on
            <a href="https://www.meetup.com/Women-in-Tech-Allies/">
              <span class="links">
                MeetUp
              </span>
            </a>
          </p>
          <h1>Check out our amazing sponsors</h1>
          <p>
            We have awesome sponsors that help us with our mission. It takes a
            great corporate culture and a true commitment to making tech culture
            more inclusive and awesome to spend the time money and talent
            actively working with us in the local community. Sounds like a great
            place to work too, huh? Check out our
            <component :is="'a'" :href="'/sponsors'" class="links">
              Sponsor Page
            </component>
            and check and check them out!
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
