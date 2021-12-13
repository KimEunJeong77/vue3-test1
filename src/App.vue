<template>
  <h1 @click="increase">{{count}} / {{doubleCount}}</h1>
  <h1 @click="changeMessage">{{message}} // {{reversedMessage}}</h1>
</template>

<script>
import {ref, computed, watch} from 'vue'
export default {
  setup(){
    const count=ref(0)
    const doubleCount=computed(()=>count.value*2 )
    const message=ref('Hello World')
    const reversedMessage=computed(()=>message.value.split('').reverse().join(''))
    
    function increase(){ count.value+=1 }
    function changeMessage(){ message.value='Good' }
    watch( message,newValue=> console.log(newValue) );
    return{
      count,increase,doubleCount,
      message,changeMessage,reversedMessage
    }
  }
}
</script>
