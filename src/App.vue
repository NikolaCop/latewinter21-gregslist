<template>
  <div class="app">
    <header class="container-fluid bg-dark text-warning">
      <div class="row p-2">
        <div class="col text-center">
          <h1 id='title'>Gregslist</h1>
          <div class="text-light">
            <router-link :to="{name: 'Home'}">Home</router-link> |
            <router-link :to="{name: 'Cars'}">Cars</router-link> |
            <router-link :to="{name: 'Houses'}">Houses</router-link> |
            <router-link :to="{name: 'Jobs'}">Jobs</router-link>
          </div>
        </div>
      </div>
    </header>
    <main>
      <router-view />
    </main>
  </div>
</template>
<style>
#icon{

}
#button{
  border-radius: 150px;
  width: 150px;
  height: 150px;
}
#welcome{
font-family: 'Covered By Your Grace', cursive;

}
#background{
  background-image: url("https://thumbs.gfycat.com/PowerfulConstantAnt-size_restricted.gif");
  background-size: cover;
}
#title {
font-family: 'Covered By Your Grace', cursive;
}
.app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

main {
  flex-grow: 1;
}

footer img {
  width: 1em;
}

a {
  color: white;
}
</style>
