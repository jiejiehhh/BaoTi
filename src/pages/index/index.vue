<template>
  <view class="content">
    <image class="logo" src="/static/logo.png" />
    <view class="text-area">
      <text class="title">{{ title }}</text>
	  
	  <button @click="handleClick"></button>
	    <text class="title">{{ test }}</text>
    </view>
  </view>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue'
import { useAppStore } from '@/store/modules/app';
import { storeToRefs } from 'pinia';

const title = ref('Hello')
const state=useAppStore()
/*const test=computed(()=>
	state.getTest
)*/
const {test}=storeToRefs(state)
const handleClick=()=>{
	state.changeVal()
}
/*function handleClick(){
	state.changeVal()
}*/
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
