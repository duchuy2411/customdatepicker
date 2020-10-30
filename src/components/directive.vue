<template>
  <div class="hello">
  </div>
</template>

<script>
export default {
  name: 'directive',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      isShow : false,
      isHide : true,
      now: 2020,
      date : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17,18,19,20,21,22,23,24,25,26,27,28,29,30],
      month : ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
      choiceMonth : null,
      isDisable: true
    }
  },
  created: function() {
    console.log(this.$route.query);
  },
}
</script>
<style scoped>

</style>