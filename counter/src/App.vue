<template>
  <div id="app">
    <input v-model="nums" />
    <img alt="Vue logo" src="./assets/logo.png" />
    <div v-if="parseInt(nums)>0">
    <Counterv-for="n in parseInt(num)"
        v-on:update="update"
        v-bind:key="n"
        v-bind:index="n"
        v-bind:counter="sum[n]"/>
    </div>
     <p>{{ getSum }}</p>
  </div>
</template>

<script>
import Counter from './components/Counter.vue'

export default {
  name: 'app',
  components: {
    Counter
  },
  data:function(){
    return {
      num: 0,
      sum: []
    }
  },
  computed: {
    getSum: function() {
      let result = 0;
      for (let item of this.sum) {
        result += item;
      }
      return result;
    }
  },
  methods: {
    update: function(param) {
      this.sum[param.index] = param.value;
    },
    initSum: function(number) {
      this.sum = [];
      for (let i = 0;i <= parseInt(number) ; i++){
        this.sum.push(i);
      }
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
