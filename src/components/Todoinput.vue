<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" placeholder="Type what you have to do" v-on:keyup.enter="addTodo">
    <span class="addContainer" v-on:keyup.enter="addTodo">
    <i class="addBtn fa fa-plus" aria-hidden="true"></i>
    </span>
    <!-- 이벤트 v-on 등록
    <button v-on:click="addTodo">추가</button>--> 
  </div>
  
</template>

<script>
export default {
  data() {
    return {
      newTodoItem : ''
      }
    }, 
  methods : {
    addTodo(){
      if(this.newTodoItem !==""){
        var value = this.newTodoItem && this.newTodoItem.trim();
        localStorage.setItem(this.newTodoItem,this.newTodoItem);
        this.clearInput;
      }},
      clearInput() {
        this.newTodoItem = '';
      }
      // localStorage 객체 내 setItem method는 로컬에 해당 데이터를  (key,value) 형태로 저장
      }
  }
</script>

<style>
input:focus{
  outline : none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius : 5px;
}
.inputBox input{
  border-style: none;
  font-size : 0.9rem;
}
.addContainer{
  float:right;
  background: linear-gradient(to right,#6478FB,#8763FB);
  display: block;
  width : 3rem;
  border-radius: 0 5px 5px 0;
}

.addBtn {
  color : white;
  vertical-align: middle;
}
</style>
