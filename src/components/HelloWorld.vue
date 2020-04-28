<template>
  <div class="hello">
    <h1>{{$store.state.count}}</h1>
    <div>
      <button @click="handleAddClick(10)">增加</button>
      <button @click="handleReduceClick(10)">减少</button>
    </div>
    <div>异步操作</div>
    <div>
      <button @click="handleActionsAdd(10)">异步增加</button>
      <button @click="handleActionsReduce(10)">异步减少</button>
    </div>
    <h4>{{ msg }}</h4>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  // count: this.$store.status.count,
  props: {
    msg: String
  },
  methods: {
      handleAddClick(n){
          this.$store.commit('mutationsAddCount',n);
      },
      handleReduceClick(n){
          this.$store.commit('mutationsReduceCount',n);
      },
      handleActionsAdd(n){
          this.$store.dispatch('actionsAddCount',n)
      },
      handleActionsReduce(n){
          this.$store.dispatch('actionsReduceCount',n)
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
