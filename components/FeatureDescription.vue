<template>
  <v-card class="feature-card">
    <v-stack align="start">
      <v-image :path="icon" :alt="title" class="feature-icon" />
      <v-stack
        direction="column"
        gap="0.5rem"
        class="feature-description-container"
      >
        <v-text :weight="600" size="1.25rem">{{ title }}</v-text>
        <ul class="list-container">
          <li
            v-for="description in descriptionList"
            :key="description"
            class="list"
          >
            <v-text class="list-description" v-html="description" />
          </li>
        </ul>
      </v-stack>
    </v-stack>
  </v-card>
</template>

<script>
export default {
  name: 'FeatureDescription',
  props: {
    icon: {
      type: String,
      default: '',
    },
    title: {
      type: String,
      default: '',
    },
    descriptionList: {
      type: Array,
      default: null,
    },
  },
}
</script>

<style lang="postcss" scoped>
@import url('./lib/media-query-helper.css');

.feature-card {
  padding: 2rem;
}

.feature-icon {
  width: 8rem;

  @media (--viewport-small) {
    width: 5rem;
  }
}

.feature-description-container {
  margin-left: 2rem;
}
</style>
