<template>
  <div
    style="min-width:200px"
    class="bg-white px-4 py-2 rounded-md shadow-md"
  >
    <div class="flex flex-row">
      <div class="">
        <div>
          {{ home }}
        </div>
        <div>
          {{ away }}
        </div>
      </div>
      <div class="ml-2">
        <div>
          {{ homeScore }}
        </div>
        <div>
          {{ awayScore }}
        </div>
      </div>
      <div class="ml-auto">
        <div>
          {{ inning }}
        </div>
        <div>
          {{ outs }}
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ScoreCard',
  props: ['home', 'away', 'home-score', 'away-score', 'inning', 'outs'],
};
</script>
<style scoped>
div {
  font-family: sans-serif;
  @apply text-sm
}
</style>