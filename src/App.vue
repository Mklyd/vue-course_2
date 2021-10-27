<template>
  <div class="container column">
    <AppForm @block-added="addBlock" />
    <AppPart :blocks="blocks" />
  </div>
  <div class="container">
    <AppLoader />
    <AppComments />
  </div>
</template>

<script>
import AppForm from './components/AppForm'
import AppPart from './components/AppPart'
import AppComments from './components/AppComments.vue'
import AppLoader from './components/AppLoader.vue'

export default {
  data() {
    return {
      blocks: [],
      
    }
  },
  methods: {

    addBlock(block) {
      this.blocks.push(block)
    }
  },
  components: {AppForm, AppPart,  AppComments, AppLoader}
}
</script>

<style>
  .avatar {
    display: flex;
    justify-content: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>
