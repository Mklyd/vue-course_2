<template>
    <form class="card card-w30" @submit.prevent="submit">
      <div class="form-control" >
        <label for="type">Тип блока</label>
        <select id="type" v-model="type">
          <option value="title" >Заголовок</option>
          <option value="subtitle">Подзаголовок</option>
          <option value="avatar">Аватар</option>
          <option value="text">Текст</option>
        </select>
      </div>

      <div class="form-control">
        <label for="value">Значение</label>
        <textarea v-model="value" id="value"></textarea>
      </div>

      <button class="btn primary" :disabled="!isValid">Добавить</button>
    </form>
</template>

<script>

export default {
  emits: ['block-added'],
    data() {
        return {
            type: 'title',
            value: ''
        }
    },
    computed: {
        isValid() {
            return this.value.length > 3
        }
    },
    methods: {
      submit() {
        this.$emit('block-added', {
          type: this.type,
          value: this.value,
        })

      this.value = ''
      this.type = 'title'
    }
    }
  
}
</script>