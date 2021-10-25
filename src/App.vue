<template>
  <app-sidebar></app-sidebar>
  <div class="container">
    <app-button></app-button>
    <app-comments></app-comments>
    <app-loader></app-loader>
  </div>
</template>

<script>
import AppSidebar from './components/AppSidebar.vue'
import AppLoader from './components/AppLoader.vue'
import AppComments from './components/AppComments.vue'
import AppButton from './components/AppButton.vue'

export default {
  components: {AppSidebar, AppLoader, AppComments, AppButton}
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
