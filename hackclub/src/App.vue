<script setup>

import {ref,computed, reactive} from 'vue'
import Footer from './Footer.vue';
const input = ref('');
const bools = computed(() => {
  return input.value!="" ? true : false
})
const list = ref([['',"Username"],['',"Password"]])
const faza = ref(0);
const lol = ref(true)
function gh(){
  if(faza.value==list.value.length){
    lol.value=false;
  }else{
  if(bools){
    list.value[faza.value][0] = input.value;
    faza.value++;
    input.value = "";
  }
}
}
function anim(){

}
/*setInterval(function(){
 

},500)*/

</script>
<template>
 <div class="center">
  <div class="rcenter">

  <form action="" @submit.prevent="gh" v-if="lol">
    
    <div class="input"><input type="text" v-model="input" :class="{ac:bools}">
      <span class="title">{{ list[faza][1] }}</span></div>
    <button><span>Next</span></button>
  </form>
  <div v-else class="sup">
    You are done now go check gmail and verify you self!
  </div>
  </div>
 </div>
 <Footer></Footer>
</template>