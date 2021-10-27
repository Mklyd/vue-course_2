<template>
    <p>
      <button class="btn primary" @click="$emit('load')">Загрузить комментарии</button>
    </p>
    <div class="card">
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item" v-for="comment in comments" :key="comment.id">
          <div >
            <p><strong>{{comment.email}}</strong></p>
            <small> {{ comment.body }}
            </small>
          </div>
        </li>
      </ul>
    </div>
</template>
<script>

export default {
  emits: ['load'],
  props: ['comments'],
}
</script>

