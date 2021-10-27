<template>
    <p>
      <button class="btn primary" @click="loadComments">Загрузить комментарии</button>
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
  data() {
    return {
      comments: [],
      id: Number,
    }
  },
  methods: {
    loadComments() {
      let json = JSON.stringify('https://jsonplaceholder.typicode.com/comments?_limit=42 ');
      this.comments = JSON.parse(json)
      console.log(this.id)
      console.log(this.comments)
    },
  }
}
</script>

