<template>
  <v-stack align="start" gap="1.25rem">
    <v-image v-if="image" :path="image" :alt="alt" class="laptop-remove tablet-remove mobile-show" />
    <v-stack direction="column" align="center" gap="1.25rem" class="blurb-container">
      <v-image v-if="image" :path="image" :alt="alt" class="mobile-remove" />
      <slot v-else name="art"></slot>
      <div>
        <v-stack direction="column" gap="0.75rem">
          <v-heading v-if="title" :level="4" :weight="600" class="blurb-title">
            {{ title }}
          </v-heading>
          <div v-if="lineBreaks">
            <div v-for="lineBreak in lineBreaks" :key="lineBreak" style="margin-top: 1.4rem" />
          </div>
          <v-text v-if="caption" font="serif" color="secondary" :weight="400" size="1rem" line-height="1.4"
            class="blurb-caption">
            {{ caption }}
          </v-text>
          <v-text v-if="description" font="serif" color="secondary" :weight="300" size="1rem" line-height="1.4"
            class="blurb-description">
            {{ description }}
          </v-text>
        </v-stack>
      </div>
    </v-stack>
  </v-stack>
</template>

<script>
export default {
  name: 'VBlurb',
  props: {
    image: {
      type: String,
      default: null,
    },
    alt: {
      type: String,
      default: null,
    },
    title: {
      type: String,
      default: null,
    },
    caption: {
      type: String,
      default: null,
    },
    description: {
      type: String,
      default: null,
    },
    lineBreaks: {
      type: Number,
      default: 0,
    },
  },
}
</script>

<style lang="postcss" scoped>
@import url('./media-query-helper.css');

.blurb-container {
  text-align: center;

  @media (--viewport-small) {
    text-align: left;
  }
}

img {
  max-width: 8rem;
}

.blurb-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 1.125rem;
  line-height: 1.375rem;

  @media (--viewport-medium) {
    font-size: 1rem;
    line-height: 1.125rem;
  }
}
</style>
