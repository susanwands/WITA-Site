<template>
  <div id="home-page" class="page-wrapper content-page">
    <site-hero
      title="About"
      subtitle=""
      image="/uploads/wita-pic-3.png"
    ></site-hero>
    <main-section theme="one-column">
      <template v-slot:default>
        <section class="content">
          <h1>How it started</h1>
          <p>
            <strong>Women in Tech Allies</strong> started in the breakroom in a
            conversation about how to get some doors open for new people in
            tech. Women trying to further their careers, parents hoping to get
            their kids more interested in tech, people looking for a place to
            make a positive impact.
          </p>

          <p>
            The first meeting was just a few people in a conference room and a
            dream.
          </p>

          <h1>How's it going</h1>
          <p>
            Our membership on MeetUp is constantly growing. It is a talented and
            diverse community with opportunities to learn, network and advance.
            We have awesome sponsors that help us with our mission. We managed
            to keep the conversation going through the pandemic by shifting
            virtual. We are looking forward getting back to in person events in
            2022!
          </p>

          <h1>Who are we anyway?</h1>
          <div class="headshots">
            <opti-image
              :src="require('~/assets/uploads/suepic.jpeg').src"
              :srcset="require('~/assets/uploads/suepic.jpeg').srcSet"
            />
          </div>

          <p>
            Susan Wands is the Founder of Women In Tech Allies (WITA), a group
            based in Raleigh-Durham with the mission to further diversity and
            inclusion in tech through networking, tech talks, mentorship and
            more. Through valuable content, a supportive environment and an
            amazing community, WITA has grown to over 1800 members and counting.
            Susan presents training on coding and technical topics in an
            approachable format and facilities sessions that showcase talented
            women in technology. She also enjoys escaping to the beach with her
            husband and son, painting, board game nights with friends and
            karaoke.
          </p>
          <div class="headshots">
            <opti-image
              :src="require('~/assets/uploads/alanipic.jpeg').src"
              :srcset="require('~/assets/uploads/alanipic.jpeg').srcSet"
            />
          </div>
          <p>
            Alani Perry is an amazing speaker, presenter and organizer. She has
            a special talent for breaking down her knowledge and experience in
            technology into fantastic workshops and trainings. As Co-Founder of
            Women In Tech Allies (WITA), Alani used her BA/PM talents to
            establish WITA's social media presence, arrange sponsorship
            opportunities, create events, mentor local talent and more.
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
.headshots {
  width: 20rem;
  height: 20rem;
  margin-bottom: 2em;
}
</style>
