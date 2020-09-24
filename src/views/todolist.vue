<template>
  <div>
    <ul>
      <li v-for="(item,index) in proc.inProc" :key="item.id" @click="proc.remove(index)">{{item.msg}}</li>
    </ul>
    <input type="text" v-model="proc.newProc.msg">
    <button @click="proc.add">添加</button>
  </div>
</template>

<script>
import { ref,reactive } from 'vue';
export default {
  name: 'todolist',
  setup() {
    let { proc } = useProcess();
    return {proc};
  }
}
function useProcess(){
  let proc = reactive({
    newProc:{msg:""},
    inProc:[
      {msg:'abc1'},
      {msg:'abc2'},
      {msg:'abc3'}
    ],
    remove(index){
      this.inProc = this.inProc.filter((newProc,idx) => idx != index);
    },
    add(){
      let newProc = Object.assign({},this.newProc)
      this.inProc.push(newProc)
      this.newProc.msg = ""
    }
  })
  return {proc};
}
</script>
<style scoped>

</style>                  