<template>
  <div
    id="app"
    class="container mx-auto"
  >
    <div class="flex flex-row justify-end">
      <button
        v-for="(item, index) in menuItems"
        :key="index"
        class="myBtn"
      >
        {{ item }}
      </button>
    </div>
    <button onclick="">
      Button
    </button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      menuItems: [
        'Home',
        'About',
        'Experience',
        'Resume',
        'Contact'
      ]
    }
  }
};
</script>

<style>
.myBtn {
}
</style>
