<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
   
  </nav> -->
  <router-view/>
</template>

<style>
/* Import Poppin font froom google font  */
@import url('https://fonts.googleapis.com/css2?family=Noto+Serif+Myanmar:wght@100;400&family=Outfit:wght@300&family=Poppins:wght@300&family=Spline+Sans:wght@300&display=swap');

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background-color: tomato;
}
</style>
