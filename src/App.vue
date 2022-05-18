<template>
  <MyButton sm>My Button</MyButton>
  <MyButton md>My Button</MyButton>
  <MyButton lg background-white>My Button</MyButton>
  <MyButton sm pill text-red background-black>My Button</MyButton>
  <MyButton md pill text-green backgound-pink>My Button</MyButton>
  <MyButton lg pill @click.prevent="onClick">My Button</MyButton>
  <MyButton type="switch" backgound-blue text-white v-model:active="active" @active="active">My Button</MyButton>
</template>

<script>
import MyButton from './components/MyButton.vue'
import {ref, onUpdated} from 'vue'

export default {
  name: 'App',
  setup(){
    const active = ref(true)
    onUpdated(()=> {
      const switchStatus = active.value?'on':'off'
      alert('switch Status: ' + switchStatus)
    })
    return {active}
  },
  methods: {
    onClick(evt) {
      alert('clicked')
    }
  },
  components: {
    MyButton
  }
}
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
