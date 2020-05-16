<template>
  <v-card
    max-width="400"
    style="height:350px"
  >
    <v-img
      class="white--text align-end"
      height="200px"
      :src="src"
    >
      <v-card-titles>
        <div class="title oop text-pirate-black text-center py-1">
          <h1> {{ title | lowercase }} </h1>
        </div>
      </v-card-titles>
    </v-img>

    <v-card-subtitle class="pb-0">
      {{ subtitle }}
    </v-card-subtitle>

    <v-card-text class="text--primary">
      <div>{{ text }}</div>
    </v-card-text>

    <v-card-actions>
      <v-btn text>
        Share
      </v-btn>

      <v-btn text>
        Preview
      </v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  name: 'HeaderCard',
  filters: {
    lowercase(value) {
      if (!value) return '';
      return value.toString().toLowerCase();
    }
  },
  props: ['title', 'subtitle', 'text', 'src'],
};
</script>
<style scoped>
.oop {
  background: linear-gradient(
    0deg,
    var(--pirate-black) 15%,
    white 15%,
    white 85%,
    var(--pirate-gold) 85%
  ) !important;
  border-radius: 2px;
}

h1 {
  font-family: PirateFont, Fallback, sans-serif !important;
  @apply text-sm;
}
</style>