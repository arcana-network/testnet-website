<template>
  <section>
    <v-container>
      <v-stack
        class="hero-section-container"
        align="start"
        sm-align="center"
        direction="column"
        gap="30px"
      >
        <v-stack
          align="start"
          sm-align="center"
          direction="column"
          sm-direction="column"
          gap="2.5rem"
          sm-gap="1.25rem"
        >
          <v-heading
            class="hero-section-heading"
            :level="1"
            :weight="700"
            line-height="1.2"
          >
            Testnet Launch
          </v-heading>
          <div>
            <v-stack
              align="start"
              sm-align="center"
              direction="column"
              sm-direction="column"
              gap="1.25rem"
              sm-gap="1.25rem"
            >
              <v-text
                class="hero-section-description"
                color="secondary"
                line-height="1.5"
                :weight="400"
              >
                Descend into the Arcana Testnet and ready our Network for
                Mainnet Arrival.
              </v-text>
              <v-text
                class="hero-section-launch"
                line-height="1.5"
                :weight="700"
              >
                Launching on 17th November, 2021
              </v-text>
            </v-stack>
          </div>
        </v-stack>
        <v-stack
          class="dn"
          align="start"
          justify="center"
          gap="1.875rem"
          sm-gap="0.9375rem"
        >
          <v-button
            :action="goToForum"
            type="button"
            label="Hunt Bugs"
            label-transform="uppercase"
            label-size="1rem"
            :label-weight="600"
          />
          <v-button
            :action="goToDeveloperDashboard"
            type="button"
            label="Build Dapps"
            label-transform="uppercase"
            label-size="1rem"
            :label-weight="600"
            variant="outline"
          />
        </v-stack>
      </v-stack>
    </v-container>
    <div class="section-gradient mobile-remove" />
  </section>
</template>

<script>
export default {
  name: 'HeroSection',
  methods: {
    goToDeveloperDashboard() {
      window.open('https://developer.arcana.network', '_blank')
    },
    goToForum() {
      window.open('https://forum.arcana.network', '_blank')
    },
  },
}
</script>

<style lang="postcss" scoped>
@import url('./lib/media-query-helper.css');

section {
  position: relative;
  min-height: calc((941 - 86) / 1440 * 100vw);

  @media (--viewport-small) {
    height: auto;
  }
}

.hero-section-container {
  margin-top: 20vh;
  float: right;

  @media (--viewport-small) {
    margin-top: calc(((451 - 86) / 375) * 100vw + 10vh);
    margin-bottom: 10vh;
    float: none;
  }
}

.hero-section-heading {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 4rem;

  @media (--viewport-small) {
    font-size: 2.1875rem;
    text-align: center;
  }
}

.hero-section-description {
  max-width: 38ch;
  font-size: 1.375rem;

  @media (--viewport-small) {
    font-size: 1rem;
    text-align: center;
    max-width: 30ch;
  }
}

.hero-section-launch {
  font-size: 1.375rem;

  @media (--viewport-small) {
    font-size: 0.875rem;
    text-align: center;
  }
}

.section-gradient {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 200px;
  background: linear-gradient(0deg, #0f0908 30%, rgba(15, 9, 8, 0) 100%);
}

.dn {
  display: none;
}
</style>