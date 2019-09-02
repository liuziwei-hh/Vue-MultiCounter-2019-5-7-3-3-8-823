<template>
  <div class="hello">
  <span>{{index}}:</span>
    <button v-on:click="clickPlus">{{ click1 }}</button>
        <span>{{number}}</span>
    <button v-on:click="clickMun">{{ click2 }}</button>
  </div>
</template>

<script>
export default {
  name: "Counter",
  props: {
    index:Number
  },
  data() {
    return {
      number: this.index,
      click1: "+",
      click2: "-",
    };
  },
  methods: {
    clickPlus: function() {
      //this.number++;
       this.$emit('update',{index:this.index, value:this.counter+1});
    },
    clickMun: function() {
      //this.number--;
    this.$emit('update',{index:this.index, value:this.counter-1})
    },
    update:function(){

    }
}
}
</script>