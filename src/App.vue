<template>
  <div>
    <p>Total {{ number }}</p>
    <LikeHeader :number="number"></LikeHeader>
    <LikeNumber :number="number" @my-click="number = $event">
      <template #title="slotProps">
        <h1>Hello!</h1>
        <h2>Nice to meet you!</h2>
        <h2>{{ slotProps.user.lastName }}</h2>
      </template>
    </LikeNumber>
    <button @click="changeHome">Home</button>
    <button @click="changeAbout">About</button>
    <keep-alive>
      <component :is="currentPage"></component>
    </keep-alive>
    <InputTest v-model="inputData"></InputTest>
    <p>{{ inputData }}</p>
  </div>
</template>

<script>
import LikeHeader from "./components/LikeHeader.vue";
import LikeNumber from "./components/LikeNumber.vue";
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import InputTest from "./components/InputTest.vue";

export default {
  data() {
    return {
      number: 10,
      currentPage: "Home",
      inputData: "aaaa",
    };
  },
  methods: {
    changeHome() {
      this.currentPage = "Home";
    },
    changeAbout() {
      this.currentPage = "About";
    },
  },
  components: {
    LikeHeader,
    LikeNumber,
    Home,
    About,
    InputTest,
  },
};
</script>