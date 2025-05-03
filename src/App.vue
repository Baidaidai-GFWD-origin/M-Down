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
    <div id="meal-container" class="w-full h-56 bg-teal-50 flex justify-center pt-10">
      <transition>
        <component :is="currentLeftComponent" class="z-20" id="component-selecter-left"></component>
      </transition>
      <transition>
        <component :is="currentMiddleComponent" class="z-10" id="component-selecter-middle"></component>
      </transition>
      <transition>
        <component :is="currentRightComponent" class="z-20" id="component-selecter-right"></component>
      </transition>
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

<style>
.v-enter-active{
  transition-property: all;
  transition-duration: 400ms;
  transition-timing-function: cubic-bezier(0.26, 1.33, 0.67, 1.50);;
}
.v-leave-active {
  transition: none;
}
.v-enter-from,
.v-leave-to {     /* 进入前/离开后完全透明 */
  transform: scale(0); /* 进入前/离开后缩小到 30% */
}
.v-enter-to{
  transform: scale(1); /* 进入后/离开前恢复到原始大小 */
}
.v-leave-from {
  transition: none;
}
</style>
