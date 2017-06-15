<template>
  <div class="hello">
    {{name}}
    <br/>
    {{msg}}
    <div class="row" v-for="(todo,index) in todos">
    <div class="col-md-4"></div>
    <div class="alert alert-warning col-md-4" role="alert">{{todo.name}}</div><div class="col-md-2"><button type="button" class="btn btn-danger" @click="deltodo(index)">DEL</button></div>
  </div>
    <form v-on:submit.prevent="addtodo(newtodo)">
      <div class="container">
        <div class="row">
        <div class="col-md-2"></div>
        <div class="col-md-8">
      <input type="text" class="form-control" placeholder="Text input" v-model="newtodo.name">
      </div >
          <div class="col-md-2  ">
      <input type="submit" class="btn btn-success">
        </div>
      </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Test',
  props:["name"],
  data () {
    return {
        msg: 'Hello Vue',
        todos:[
            {name:"Lee"}, {name:"Lov3"},{name:"Lov3ling"}
        ],
        newtodo:{name:""},
    }
  },
    methods:{
      addtodo(newtodo){
          this.todos.push(newtodo);
          this.newtodo={name:""};
      },
        deltodo(index){
          this.todos.splice(index,1);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
