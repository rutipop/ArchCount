<template>
  <div class="background">
    <div  class="main">
      <div class="logo">
        <img class="main-logo" :src="archCountLogo"/>
      <div class="title" v-text="ARCH_COUNT_TITLE"/>
      </div>
      <div class="adding">
        <div class="select-box"> </div>
        <custom-button :text="ADD_BTN" :width="48" background-color="#c36871"/>
      </div>
      <custom-button :text="HISTORY_BTN" :width="300"/>
    </div>
  </div>
</template>

<script>
import archCountLogo from '../assets/target.png'
import { HISTORY_BTN, ADD_BTN, ARCH_COUNT_TITLE } from '../const';
import CustomButton from './CustomButton.vue'

export default {
  name: 'MainPage',
  components: {
    CustomButton
  },
  props: {
  },
  data() {
    return {
      archCountLogo,
      HISTORY_BTN,
      ADD_BTN,
      ARCH_COUNT_TITLE,
    }
  }
}
</script>

<style scoped>
.background{
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
  position: absolute;
  left: 0;
  top: 0;
  background: linear-gradient(45deg,  #9d353c,
  #c9c9ce,
  #7f96b3,
  #a84a59,
  #d1ae55);
 
  background-size: 1000% 1000%;
  animation: rainbow 20s ease infinite;

}
.main{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: black;
  cursor: default;
  font-family: "Work Sans", sans-serif;
  font-weight: 800;
  font-size: 5em;
  line-height: 0.9em;

  position: absolute;
  top: 50%;
  left: 50%;
  transform-origin: center;

  animation: jumpIn 1500ms cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;

  
}

.logo{
  display: flex;
  flex-direction: column;
  position: relative;
  align-items: center;
  margin-bottom: 48px;
  


}
.title{
  font-size: 60px;
  color: black;
  position: absolute;
  top: 245px;
}

.main-logo{
  width: 300px;
  height: 300px;

}
.adding{
  display: flex;
  gap: 12px;
  align-items: center;
  margin-bottom: 24px;
}

.select-box{
  width: 132px;
  height: 32px;
  border: 2px solid black;
  border-radius: 16px;
}

/** keyframs: */

@keyframes jumpIn {
  0% {
    transform: translate(-50%, -50%) scale(0);
  }
  60% {
    transform: translate(-50%, -50%) scale(1.2);
  }
  100% {
    transform: translate(-50%, -50%) scale(1);
  }
}
@keyframes rainbow {
  0%{background-position:0% 82%}
  50%{background-position:100% 19%}
  100%{background-position:0% 82%}
}

</style>
