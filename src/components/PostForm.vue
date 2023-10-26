<script>
export default {
  data: () => {
    return {
      title: "",
      body: "",
    };
  },
  methods: {
    createPost() {
      this.$emit("createPost", this.title, this.body);
      this.title = "";
      this.body = "";
    },
  },
};
</script>

<template>
  <form>
    <input type="text" class="input" placeholder="Название" v-model="title" />
    <input type="text" class="input" placeholder="Описание" v-model="body" />
    <button :disabled="!title || !body" @click.prevent="createPost" class="btn">
      Создать
    </button>
  </form>
</template>

<style scoped></style>
