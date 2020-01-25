<template>
  <div id="app">
    <input type="text" v-model="todox" placeholder="escreve todo" class="formato">
    <button @click="add" class="adicionar">Adicionar</button>
    <div v-for="(item, index) in list" :key="item">
      {{item}}
      {{index}}
      <button @click="remover(index)" class="remover">o</button>
    </div>
  </div>
</template>
<script>
export default {
  data(){
    return{
      todox: '',
      list: [],
    }
  },
  methods:  {
    add() {
      this.list.push(this.todox);
      this.todox = "";
    },
    remover(index){
        this.list.splice(index, 1);
    }
  }
}
</script>
<style lang="scss">
.template{
  background-color: gray;
}
.formato{
    border-radius: 3%;
}
.remover{
  border-radius: 100%;
  background-color: red;
}
.adicionar{
  background-color: gray;
  color: antiquewhite;
  border-radius: 1%; 
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
        
      
    
    
      
