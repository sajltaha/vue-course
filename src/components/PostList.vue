<script>
import PostItem from "./PostItem.vue";
export default {
  components: { PostItem },
  emits: ["delete-post"],
  props: {
    posts: {
      type: Array,
      required: true,
      default: [],
    },
  },
};
</script>

<template>
  <h2>Список постов</h2>
  <post-item
    v-for="post in posts"
    :key="post.id"
    :post="post"
    @delete-post="$emit('delete-post', post.id)"
  />
</template>

<style scoped></style>
