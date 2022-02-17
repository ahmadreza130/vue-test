<template>
  <div>
    <h5>insert information</h5>
    <input type="text" placeholder="text" v-model="text" />
    <input type="number" placeholder="user" v-model="user" />
    <button @click="cliclHandeler">create</button>
  </div>
</template>
<script>
export default {
  name: "create",
  data() {
    return {
      user: null,
      text: "",
    };
  },
  props: {
    create: Function,
  },
  methods: {
    cliclHandeler() {
      this.create(this.text, this.user);
      this.text = "";
      this.user = null;
    },
  },
};
</script>
