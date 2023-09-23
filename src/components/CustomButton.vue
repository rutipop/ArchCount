<template>
    <div class="button" :style='customStyle'>
        {{ text }}
    </div>
</template>
  
<script>

export default {
name: 'CustomButton',
props: {
    text:{
        type: String,
        default: ''
    },
    height:{
        type: Number,
        default: 0
    },
    width:{
        type: Number,
        default: 0
    },
    borderColor: {
        type: String,
        default: ''
    },
    backgroundColor: {
        type: String,
        default: ''
    }
},
data() {
    return {

    }
},
computed: {
    customStyle() {
        return{
        ...(this.height? {height: `${this.height}px`} : {}),
        ...(this.width? {width: `${this.width}px`} : {}),
        ...(this.borderColor? {borderColor: this.borderColor} : {}),
        ...(this.backgroundColor? {backgroundColor: this.backgroundColor} : {})
        };
    }
}
}
</script>

<style scoped>

.button{
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #c9c9ce;
    width: 48px;
    height: 32px;
    border: 2px solid black;
    border-radius: 24px;
    cursor: pointer;
    padding: 4px;
    font-size: 16px;
    background-size: 400% 400%;
    box-shadow: 6px 6px 0;


}
.button:hover {
    animation: gradient 10s ease infinite;
    box-shadow: 2px 2px 0;
}

@keyframes gradientMove {
  0% {
    background-position: 0% 0%;
  }
  100% {
    background-position: 100% 100%;
  }
}
@keyframes gradient {
  50% {
    background-position: 100% 0;
  }
}

</style>
