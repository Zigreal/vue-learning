<template>
  <div class="app">
    <post-form
      @create="createPost"
    />
    <post-list
      :posts="posts"
    />
  </div>
</template>

<script>
import PostForm from "./components/PostForm.vue";
import PostList from "./components/PostList.vue";
export default {
  components: {
    PostForm, PostList
  },
  name: "App",
  data() {
    return {
      likes: 0,
      dislikes: 0,
      posts: [
        {id: 1, title: 'Javascript 1', body: 'Описание поста 1'},
        {id: 2, title: 'Javascript 2', body: 'Описание поста 2'},
        {id: 3, title: 'Javascript 3', body: 'Описание поста 3'},
        {id: 4, title: 'Javascript 4', body: 'Описание поста 4'}
      ]
    }
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislikes += 1;
    },
    createPost(post) {
      this.posts.push(post);
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
</style>