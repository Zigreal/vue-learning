<template>
  <h4>Создание поста</h4>
  <form @submit.prevent>
    <input
     v-model="post.title"
      class="post-input"
      type="text"
      placeholder="Название"
    >
    <input
      v-model="post.body"
      class="post-input"
      type="text"
      placeholder="Описание"
    >
    <button
      class="btn"
     @click="createPost"
    >
      Создать
    </button>
  </form>


</template>

<script>
export default {
  name: "PostForm",
  emits: ['create'],
  data() {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    }
  }
}
</script>

<style scoped>
.post-input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  margin-top: 15px;
  align-self: self-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

form {
  display: flex;
  flex-direction: column;
}
</style>