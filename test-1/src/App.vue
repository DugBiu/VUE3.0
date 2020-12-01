<template>
<div>
  <img alt="Vue logo" src="./assets/logo.png">
  <h2>欢迎光临点餐中心</h2>
  <div>请选择一位服务员为您服务</div>
  <div>
    <button
      v-for="(item, index) in waiter"
      v-bind:key="index"
      @click="selectWaiterfn(index)"
    >
      {{ `${index}:${item}`}}
      </button>
  </div>
  <div>你选择了【{{ selectWaiter }}】服务员为你服务</div>
</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'App',
  setup() {
    const waiter = ref(['Alias', 'Jack', 'smith'])
    const selectWaiter = ref('')
    const selectWaiterfn = (index: number)=>{
      selectWaiter.value = waiter.value[index]
    }
    return {
      waiter,
      selectWaiter,
      selectWaiterfn
    } 
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
