<script setup>
  import FigmaIcon from './components/icnos/FigmaIcon.vue';
  import GithubIcon from './components/icnos/GithubIcon.vue';
  import { ref } from 'vue';

  let currentLeftComponent = ref(FigmaIcon)
  let currentMiddleComponent = ref(FigmaIcon)
  let currentRightComponent = ref(FigmaIcon)

  function changeLeft(param = FigmaIcon){
    currentLeftComponent.value = param
  }
  function changeMiddle(param = FigmaIcon){
    currentMiddleComponent.value = param
  }
  function changeRight(param = FigmaIcon){
    currentRightComponent.value = param
  }

</script>
<template>
  <div id="menu-whole-container" class=" h-screen w-screen flex flex-col">
    <div id="meal-container" class=" w-full h-56 bg-teal-50 flex justify-center pt-10">
      <component :is="currentLeftComponent" class="relative  translate-x-5 z-20" id="component-selecter-left"></component>
      <component :is="currentMiddleComponent" class="relative  translate-y-5 z-10" id="component-selecter-middle"></component>
      <component :is="currentRightComponent" class="relative  -translate-x-5 z-20" id="component-selecter-right"></component>
    </div>
    <div id="meal-selector" class="bg-violet-50 grow flex flex-col w-full justify-around items-center">
      <div id="left-selector">
        <div class=" w-28 h-8 rounded-2xl bg-violet-200 flex">
          <p class="m-auto">Left Selector</p>
        </div>
        <button class=" m-4 w-16 h-12 rounded-2xl bg-violet-200" @click="changeLeft()">Figma</button>
        <button class=" m-4 w-16 h-12 rounded-2xl bg-violet-200" @click="changeLeft(GithubIcon)">Github</button>
      </div>
      <div id="mid-selector">
        <div class=" w-32 h-8 rounded-2xl bg-violet-200 flex">
          <p class="m-auto">Middle Selector</p>
        </div>
        <button class=" m-4 w-16 h-12 rounded-2xl bg-violet-200" @click="changeMiddle()">Figma</button>
        <button class=" m-4 w-16 h-12 rounded-2xl bg-violet-200" @click="changeMiddle(GithubIcon)">Github</button>
      </div>
      <div id="right-selector">
        <div class=" w-32 h-8 rounded-2xl bg-violet-200 flex">
          <p class="m-auto">Right Selector</p>
        </div>
        <button class=" m-4 w-16 h-12 rounded-2xl bg-violet-200" @click="changeRight()">Figma</button>
        <button class=" m-4 w-16 h-12 rounded-2xl bg-violet-200" @click="changeRight(GithubIcon)">Github</button>
      </div>
      
    </div>
  </div>
</template>