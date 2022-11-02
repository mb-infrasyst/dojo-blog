<template>
  <div class="home">
    <h1>home</h1>
    <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from "@vue/reactivity";
export default {
  name: "Home",
  setup() {
    // const p = ref(null);

    // let text = "Hello World!";
    // let result = text.toUpperCase();

    const name = ref("mario");
    const age = ref(30);
    // const textallcapsout = ref("hello melvin, the man!")

    const handleClick = () => {
      name.value = "luigi";
      age.value = 35;
      // textallcapsout.value = textallcapsout.value.toUpperCase()
    };

    return {
      name,
      age,
      handleClick,
    };
  },
};
</script>
