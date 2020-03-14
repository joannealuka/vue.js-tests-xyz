<template>
  <div id="app">
    <navbar />
    <div class="container">
      <router-view />
    </div>
    <foo />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Foo from "@/components/Foo.vue";

export default {
  components: {
    Navbar,
    Foo
  }
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

img {
  height: 100%;
  width: 100%;
  object-fit: cover;
}

body {
  background: #f1f1f1;
  color: #333;
}

.container {
  margin-top: 70px;
  padding: 20px;
  position: relative;
}
</style>
