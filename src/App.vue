<template>
  <div id="app">
    <header>
      <nav>
        <ul>
          <li>Weather</li>
          <li class="dropdown">
            <a href="#" class="dropbtn">Tasks</a>
            <div class="dropdown-content">
              <a href="https://tugas1-pbk-223510005.vercel.app/" target="_blank">Task 1</a>
              <a href="https://223510005-tugas2pbk-muhammadazizi.vercel.app/" target="_blank">Task 2</a>
              <a href="https://tugas3pbk-muhammadazizi-223510005.vercel.app/" target="_blank">Task 3</a>
              <a href="https://tugas4-pbk-223510005.vercel.app/" target="_blank">Task 4</a>
              <a href="https://muhammadazizi-223510005-pr5.vercel.app/" target="_blank">Task 5</a>
              <a href="https://tugas6-pbk-223510005-muhammadazizi.vercel.app/" target="_blank">Task 6</a>
              <a href="https://tugas7-pbk-223510005-muhammad-azizi.vercel.app/" target="_blank">Task 7</a>
            </div>
          </li>
        </ul>
      </nav>
    </header>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
#app {
  text-align: center;
}

header {
  background: #ff9a9e;
  padding: 50px;
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

nav li {
  display: inline-block;
  margin-right: 20px;
  margin-left: 20px;
  font-size: 24px; 
  font-weight: bold;
}

nav a {
  color: #fff;
  text-decoration: none;
  padding: 5px 10px;
}

nav a:hover {
  text-decoration: underline;
}

.dropdown {
  position: relative;
  display: inline-block;
  font-size: 24px; 
  font-weight: bold;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 100px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {
  background-color: #f1f1f1;
}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown:hover .dropbtn {
  background-color: #000000;
}
</style>
