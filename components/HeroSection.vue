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
          <div>
            <v-heading
              class="hero-section-heading-em"
              :level="3"
              :weight="700"
              line-height="1.2"
            >
              Arcana Beta Testnet
            </v-heading>
            <v-heading
              class="hero-section-heading-em"
              :level="1"
              :weight="700"
              line-height="1.2"
            >
              Quantum Ascent
            </v-heading>
          </div>
          <div>
            <v-heading
              class="hero-section-heading"
              line-height="1.2"
              :weight="600"
              font="serif"
            >
              Welcome!
            </v-heading>
            <v-stack gap="0.5rem">
              <v-text
                class="hero-section-launch"
                line-height="1.5"
                :weight="500"
              >
                It's time to put privacy front and center.
              </v-text>
              <v-text
                class="hero-section-launch"
                line-height="1.5"
                :weight="700"
              >
                Let's build.
              </v-text>
            </v-stack>
          </div>
        </v-stack>
        <v-stack
          align="center"
          direction="row"
          sm-direction="column"
          justify="center"
          gap="2rem"
          sm-gap="1rem"
          wrap
        >
          <v-button
            class="cta-button"
            :action="() => handleViewDocs()"
            type="button"
            label="View Docs"
            label-transform="uppercase"
            label-size="1rem"
            :label-weight="600"
          />
          <v-button
            class="cta-button"
            :action="() => handleGoToDashboard()"
            variant="outline"
            label="Go to Dashboard"
            label-transform="uppercase"
            label-size="1rem"
            :label-weight="600"
          />
          <a
            :href="ARCANA_DISCORD_URL"
            target="_blank"
            title="Join Discord"
            class="cta-icon"
          >
            <img src="@/assets/images/discord.svg" alt="Join Discord" />
          </a>
        </v-stack>
      </v-stack>
    </v-container>
    <div class="section-gradient tablet-remove mobile-remove" />
  </section>
</template>

<script>
const ARCANA_DISCORD_URL = process.env.ARCANA_DISCORD_URL

export default {
  name: 'HeroSection',
  data() {
    return {
      ARCANA_DISCORD_URL,
    }
  },
  methods: {
    handleViewDocs() {
      window.open('https://docs.beta.arcana.network', '_blank')
    },
    handleGoToDashboard() {
      window.open('https://dashboard.beta.arcana.network', '_blank')
    },
  },
}
</script>

<style lang="postcss" scoped>
@import url('./lib/media-query-helper.css');

section {
  position: relative;
  min-height: calc((856 - 86) / 1440 * 100vw);

  @media (--viewport-small) {
    height: auto;
    min-height: unset;
  }
}

.hero-section-container {
  margin-top: 12vh;
  float: right;

  @media (--viewport-small) {
    margin-top: calc(((451 - 86) / 375) * 100vw + 12vh);
    margin-bottom: 10vh;
    float: none;
  }
}

.hero-section-heading {
  margin-top: 0;
  margin-bottom: 0.625rem;
  font-size: 2rem;

  @media (--viewport-small) {
    font-size: 1.5rem;
    text-align: center;
  }
}

.hero-section-heading-em {
  margin-top: 0;
  margin-bottom: 0;
  max-width: 44rem;

  @media (--viewport-small) {
    text-align: center;
  }
}

.hero-section-heading-em:first-child {
  font-size: 1.125rem;
  text-transform: uppercase;
  margin-bottom: 0.625rem;
  letter-spacing: 0.375rem;
}

.hero-section-heading-em:nth-child(2) {
  font-size: 3.875rem;

  @media (--viewport-small) {
    font-size: 2.5rem;
  }
}

.hero-section-launch {
  font-size: 1.375rem;
  max-width: 38ch;

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
  background: linear-gradient(0deg, #121212 24.79%, rgba(18, 18, 18, 0) 98.31%);
}

.cta-button {
  padding: 0;
  width: 14.375rem;
  height: 3.125rem;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px !important;

  @media (--viewport-small) {
    margin-top: 1rem;
  }
}

.cta-icon {
  vertical-align: middle;
}

.cta-icon > img {
  height: 3.125rem;
  vertical-align: middle;
}

@media (--viewport-small) {
  .cta-icon {
    margin-top: 1rem;
  }
}
</style>
