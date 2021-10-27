<template>
  <div class="container column">
    <AppForm @block-added="addBlock" />
    <AppPart :blocks="blocks" />
  </div>
  <div class="container">
    <AppLoader />
    <AppComments 
      :comments="comments"
      @load="loadComments"
    />
  </div>
</template>

<script>
import AppForm from './components/AppForm'
import AppPart from './components/AppPart'
import AppComments from './components/AppComments.vue'
import AppLoader from './components/AppLoader.vue'

import axios from 'axios'

export default {
  data() {
    return {
      blocks: [],
      comments: []
    }
  },
  methods: {
    async loadComments() {
      const { data} = await axios.get('https://jsonplaceholder.typicode.com/comments?_limit=42')
      console.log(data)
      const result = Object.keys(data).map(key => {
        return {
          id: key,
          ...data[key]
        }
      })
      this.comments = result
    },
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
