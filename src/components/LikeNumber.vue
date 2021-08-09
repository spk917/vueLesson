<template>
  <div>
    <slot name="title" :user="user"></slot>
    <p>good({{ number / 2 }})</p>
    <button @click="inclement">+1</button>
  </div>
</template>

<script>
export default {
  props: ["number"],
  data() {
    return {
      user: {
        lastName: "Mike",
      },
    };
  },
  methods: {
    inclement() {
      this.$emit("my-click", this.number + 1);
    },
  },
};
</script>
