<script>
import PostList from "./components/PostList.vue";
import MyModal from "./components/UI/MyModal.vue";
export default {
  components: { PostForm, PostList, MyModal },
  data: () => {
    return {
      posts: [
        {
          id: 1,
          title: "Javascript 1",
          body: "Description of post 1",
        },
        {
          id: 2,
          title: "Javascript 2",
          body: "Description of post 2",
        },
        {
          id: 3,
          title: "Javascript 3",
          body: "Description of post 3",
        },
      ],
    };
  },
  methods: {
    createPost(title, body) {
      const newPost = {
        id: Date.now(),
        title: title,
        body: body,
      };
      this.posts.push(newPost);
    },
    deletePost(id) {
      this.posts = this.posts.filter((post) => post.id !== id);
    },
  },
};
</script>

<template>
  <div class="app">
    <!-- <post-form @create-post="createPost" /> -->
    <button  >Click</button>
    <post-list :posts="posts" @delete-post="deletePost" />
  </div>
</template>

<style>
.app {
  padding: 20px;
}

form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin: 15px 0 0 0;
}

.btn {
  align-self: flex-end;
  margin-top: 15px;
  border: 1px solid teal;
  padding: 10px 15px;
  background: none;
  color: teal;
}

.post {
  padding: 15px;
  border: 2px solid teal;
  margin: 15px 0 0 0;
}
</style>
