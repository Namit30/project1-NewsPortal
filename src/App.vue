<template>
  <nav>
    <router-link to="/">News</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
 
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: linear-gradient(45deg, #f3f5f9, #dde1e7);
  min-height: 100vh;
  padding: 20px;
  position: relative;
  overflow: hidden; /* hide any out-of-bounds pseudo elements */
}

#app::before {
  content: "";
  position: absolute;
  top: 0;
  left: 50%;
  width: 600px;
  height: 600px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  transform: translate(-50%, -50%) rotate(45deg); 
  pointer-events: none; /* ensure it doesn't interfere with any interactions */
}

nav {
  padding: 30px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: rgba(255, 255, 255, 0.8); /* semi-transparent background */
  border-radius: 8px;
  transform: translateY(0); /* initial state */
  transition: transform 0.2s; /* smooth movement */
}

nav:hover {
  transform: translateY(-5px); /* slightly raises the nav on hover */
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 5px 10px;
  transition: all 0.3s;
  border-radius: 4px; /* rounded corners for the hover effect's background */
  position: relative; 
  overflow: hidden; /* hide overflowing content like the after pseudo-element */
}

nav a::after { 
  /* creating an underlining effect */
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: #42b983;
  transition: width 0.3s;
}

nav a:hover {
  background-color: #42b983;
  color: white;
}

nav a:hover::after {
  width: 100%; /* full underline on hover */
}

nav a.router-link-exact-active {
  color: #42b983;
}

h4 {
  font-size: 20px;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
}

</style>
