<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts"/>
    <button @click="showPosts = !showPosts">toogle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "@vue/reactivity";
import { computed, watch, watchEffect } from "@vue/runtime-core";
export default {
  name: "Home",
  components: { PostList },
  setup() {
    const posts = ref([
      { title: "welcome to the blog", body: "Quisque imperdiet eget nunc at consequat. Praesent euismod a magna eget efficitur. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Sed tincidunt vehicula sollicitudin. Quisque nec porttitor leo. Donec maximus, turpis tincidunt cursus ornare, neque mi iaculis velit, ut bibendum massa odio nec erat. Aenean sed urna ante. Donec fringilla, mauris eu sagittis rutrum, ipsum mi fermentum turpis, ut consequat est ipsum quis sem. Ut hendrerit elit vitae ante dignissim aliquam. Maecenas varius tempor scelerisque. Sed sodales dignissim lobortis. In tristique, est id iaculis congue, sem nisi porta felis, blandit pulvinar enim erat ultricies justo. Mauris vulputate leo lorem, at lobortis nibh cursus non. Cras id quam varius, vestibulum libero in, tincidunt lorem.", id: 1 },
      { title: "top 5 CSS tips", body: "lorem ipsum", id: 2 },
    ]);

    const showPosts = ref(true)

    return { posts, showPosts };
  },
};
</script>
