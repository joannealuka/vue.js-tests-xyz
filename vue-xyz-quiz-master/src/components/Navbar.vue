<template>
  <nav class="navbar">
    <div class="logo">
      <router-link to="/">
        <h1>Logo</h1>
      </router-link>
    </div>
    <menu class="menu">
      <ul>
        <li>
          <router-link to="/">Home</router-link>
        </li>
        <li>
          <router-link to="#!">About</router-link>
        </li>
        <li>
          <router-link to="#!">Contact</router-link>
        </li>
      </ul>
    </menu>
    <div class="search">
      <input type="text" class="search" placeholder="Search" />
    </div>
  </nav>
</template>

<script>
export default {
  name: "navbar"
};
</script>

<style lang="scss" scoped>
.navbar {
  padding: 15px 45px;
  position: fixed;
  top: 0%;
  left: 0%;
  width: 100%;
  border-bottom: solid 1px #ddd;
  background: #fff;

  display: flex;
  align-items: center;
  justify-content: space-between;
  z-index: 1;

  a {
    color: teal;
    text-decoration: none;
  }

  .menu ul {
    list-style: none;
    display: flex;
    align-items: center;
    justify-content: center;

    a {
      margin: 0 20px;
      text-decoration: none;
      display: block;
      color: #333;

      &:hover {
        color: teal;
      }
    }
  }

  .search input {
    padding: 10px;
    display: block;
    border-radius: 10px;
    border: solid 2px #ddd;
    transition: 0.2s ease-in-out;
    outline: none;

    &::placeholder {
      color: #ddd;
    }

    &:focus {
      border-color: teal;
    }
  }
}
</style>