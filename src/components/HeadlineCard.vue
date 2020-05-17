<template>
  <div
    style="height:350px; min-width:343px;"
    class="bg-white rounded-md shadow-md flex flex-col"
  >
    <img
      class="object-cover h-48 w-full rounded-t-md"
      height="200px"
      :src="src"
    >

    <div class="title oop text-pirate-black text-center py-2 flex flex-row items-center justify-around">
      <h1> {{ title | lowercase }} </h1>
    </div>

    <div class="mx-4 my-2">
      <div class="subtitle pb-0 text-gray-700">
        {{ subtitle }}
      </div>

      <div class="low-text text-sm">
        <div>{{ text }}</div>
      </div>
    </div>
    <div class="mx-4 mt-2 flex flex-row justify-end">
      <button
        v-for="b in buttons"
        :key="b"
        class="ml-2"
      >
        <i :class="b" />
      </button>
    </div>
  </div>
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
  data() {
    return {
      buttons: [
        'fab fa-twitter',
        'fab fa-facebook-f',
        'fas fa-share-square'
      ]
    }
  }
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
}

.subtitle {
  @apply text-sm;
}

i {
  @apply text-lg
}

h1 {
  font-family: PirateFont, Fallback, sans-serif !important;
  @apply text-sm;
}

button {
  @apply px-1 py-1 rounded-sm
}

button:hover {
  @apply text-pirate-gold
}
</style>