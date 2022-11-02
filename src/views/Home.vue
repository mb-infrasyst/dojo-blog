<template>
  <div class="home">
    <h1>home</h1>
    <p ref="par">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
export default {
  name: "Home",
  setup() {
    console.log(this);

    const par = ref('hello')
    console.log(par, par.value)

    let name = "mario";
    let age = 30;

    const handleClick = () => {
      console.log(par, par.value);
      par.value.classList.add("test")
      par.value.textContent = "Hello, ninjas."
    };

    return {
      name,
      age,
      handleClick,
      par
    };
  },
};
</script>
