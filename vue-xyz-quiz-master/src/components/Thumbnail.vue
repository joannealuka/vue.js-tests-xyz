<template>
  <div class="thumbnail">
    <div class="head">
      <router-link :to="url">
        <img :src="image" :alt="name" />
      </router-link>
    </div>
    <div class="body">
      <router-link :to="url">
        <h2 class="name">{{name}}</h2>
      </router-link>
      <h4 class="department">{{department}}</h4>
    </div>
  </div>
</template>

<script>
export default {
  name: "card",
  props: {
    avatar: String,
    name: String,
    department: String,
    slug: String
  },
  computed: {
    image() {
      return require(`@/assets/employees/${this.avatar}`);
    },
    url() {
      return `/employee/${this.slug}`;
    }
  }
};
</script>

<style lang="scss" scoped>
.thumbnail {
  margin: 40px;
  width: 100%;
  max-width: 300px;
  background: #fff;
  border-radius: 10px;
  border: solid 1px #ddd;
  overflow: hidden;

  .head {
    height: 250px;
    width: 100%;
    overflow: hidden;
  }

  .body {
    padding: 20px;
    line-height: 2em;

    a {
      color: teal;
      text-decoration: none;
    }

    .department {
      color: #999;
    }
  }
}
</style>