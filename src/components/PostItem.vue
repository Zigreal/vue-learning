<template>
  <div class="post">
    <div><strong>Название:</strong> {{ post.title }}</div>
    <div><strong>Описание:</strong> {{ post.body }}</div>
    <div>
      <button @click="addLike">Like!</button>
      <button @click="addDislike">Dislike!</button>
    </div>
    <div>Кол-во лайков: <strong>{{ likes }}</strong></div>
    <div>Кол-во дизлайков: <strong>{{ dislikes }}</strong></div>
  </div>
</template>

<script>
export default {
  name: "PostItem",
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid;
  margin-top: 15px;
}
</style>