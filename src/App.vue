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
<teleport to="#modals" v-if="showModal">
  <Modal :arrayy="['ar1', 123]" theme="sale"  @close="toggleModal">
    <template v-slot:links>
      <a href="#">Sign up</a>
      <a href="#">more info</a>
    </template>      
    <h1>Hi Ghazal</h1>
    <p>some texr here!</p>
  </Modal>
</teleport>
<button class="btn btn-primary" @click.alt="toggleModal">open modal (+alt)</button>
</template>

<script>
export default {
  data() {
    return {
      title: "vue js 3 training",
      subTitle: '',
      showModal: false
    }
  },
  components: {
    Modal
  },
  methods: {
    handleClick() {
      this.subTitle = this.$refs.name.value
    },
    toggleModal() {
      this.showModal = !this.showModal
    }
  }
}
</script>