<template>
  <div class="card card-w70">
    <template v-if="blocks.length">
      <component
        v-for="block in blocks"
        :key="block"
        :is="'app-' + block.type"
        v-bind="{value: block.value}"
      ></component>
    </template>
    <h3 v-else>Добавьте первый блок, чтобы увидеть результат</h3>
  </div>
</template> 
<script>
import AppTitle from './parts/AppTitle.vue'
import AppAvatar from './parts/AppAvatar.vue'
import AppSubtitle from './parts/AppSubtitle.vue'
import AppText from './parts/AppText.vue'

export default {
    props: ['blocks'],
    components: { AppTitle, AppAvatar, AppSubtitle, AppText}
}
</script>