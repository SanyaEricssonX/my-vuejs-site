<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <input
      v-model="post.title"
      class="input"
      type="text"
      placeholder="Название"
    />
    <input
      v-model="post.body"
      class="input"
      type="text"
      placeholder="Описание"
    />
    <my-button class="btn create__btn" @click="createPost">Создать</my-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 1px solid teal;
  margin-top: 15px;
  padding: 10px 15px;
}
.create__btn {
  align-self: flex-end;
  margin-top: 15px;
}
</style>

