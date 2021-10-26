<template>
    <div class="card card-w70" >
        <template>
            <component
            v-for="block in blocks"
            :key="block.id"
            :is="'resume' + block.type"
            v-bind="{value: block.value }"
            >
            </component>
        </template>

    </div>
   

</template>
<script>
import AppTitle from './parts/AppTitle'
import AppAvatar from './parts/AppAvatar.vue'
import AppSkills from './parts/AppSkills.vue'
import AppText from './parts/AppText.vue'

export default {
    props: ['blocks'],
    components: { AppTitle, AppAvatar, AppSkills, AppText}
}
</script>