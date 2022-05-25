<template>
  <div>
 <div class="box">
          <div>One</div>
          <div>Two</div>
          <div>Three
              <br>has
              <br>extra
              <br>text
          </div>
        </div>
  </div>
</template>

<script>

function debounce (fn, delay) {
  return function () {
    let args = arguments
    if(fn.id) clearTimeout(fn.id)
    setTimeout(() => {
      fn.apply(this, arguments)
    }, delay)
  }
}

function throttle (fn, delay) {
  let last, timer
  return function () {
    let args = arguments
    let now = Date.now()
    if (last && now < last + delay) {
      last = now
      clearTimeout(timer)
      setTimeout(() => {
        fn.apply(this, args)
      }, delay)
    } else {
      last = now
      fn.apply(this, args)
    }
  }
}

export default {
  name: "test",

  components: {},

  props: {},

  data() {
    return {};
  },

  computed: {},

  watch: {},

  mounted() {
    function getStrLength (str) {
      if (str) {
        let arr = str.split(' ')
        console.log(arr[arr.length-1].length)
      } else {
        console.log(0)
      }
    }
    let str = 'my name is hanbingbing'
    getStrLength(str)
  },

  methods: {}
};
</script>

<style>
 .box {
            display: flex;
            flex-direction: row-reverse;
          }
</style>
