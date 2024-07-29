<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-logo">
        <a href="#">DataCat</a>
      </div>
      <ul class="navbar-menu">
        <li class="navbar-item"><a href="#">Add Employee</a></li>
        </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar'
};
</script>

<style scoped>
.navbar {
  background-color: #333;
  padding: 1rem;
  color: #fff;
}

.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar-logo a {
  color: #fff;
  text-decoration: none;
  font-size: 1.5rem;
}

.navbar-menu {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;
}

.navbar-item {
  margin-left: 1.5rem;
}

.navbar-item a {
  color: #fff;
  text-decoration: none;
  font-size: 1rem;
}

.navbar-item a:hover {
  text-decoration: underline;
}
</style>
