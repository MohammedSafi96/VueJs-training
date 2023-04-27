<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Modal from './components/Modal.vue'
</script>

<template>
  <!-- <RouterView /> -->
 <div>  
  <h1> {{ title }} </h1>
  <h3>{{ subTitle }}</h3>
 </div>
  <br>
 <div>
  <input type="text" ref="name">
  <button class="btn btn-primary" @click="handleClick">click me</button>
 </div>

 <Modal />
</template>

<script>  
export default {
  data(){
    return {
      title: "vue js 3 training",
      subTitle: ''
    }
  },
  components: {
    Modal
  },
  methods: {
    handleClick() {
      this.subTitle = this.$refs.name.value
    }
  }
}
</script>