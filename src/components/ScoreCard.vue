<template>
  <v-card min-width="225">
    <v-card-text class="text--primary flex flex-row">
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
    </v-card-text>
  </v-card>
</template>
<script>
export default {
  name: 'ScoreCard',
  props: ['home', 'away', 'home-score', 'away-score', 'inning', 'outs'],
};
</script>