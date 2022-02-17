<template>
  <h5>id:{{ resume.id }}</h5>
  <h5>user:{{ resume.user }}</h5>
  <p>{{ resume.text }}</p>
  <button @click="dlt(resume.id)">delete</button>
  <button
    @click="
      () => {
        showEdit = !showEdit;
      }
    "
  >
    edit
  </button>
  <div v-if="showEdit">
    <input type="text" v-model="newText" />
    <input type="number" v-model="newUser" />
    <button
      @click="
        edit(resume.id, newText, newUser);
        showEdit = false;
      "
    >
      change
    </button>
  </div>

  <hr  />
</template>
<script>
export default {
  name: "Resume",
  props: {
    resume: Object,
    dlt: Function,
    edit: Function,
  },
  data() {
    return {
      newText: this.resume.text,
      newUser: this.resume.user,
      showEdit: false,
    };
  },
};
</script>
