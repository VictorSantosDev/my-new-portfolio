<template>
  <nav id="nav-main">
    <div id="logo">
      Portfolio
    </div>

    <div id="nav-buttons">
      <a href="#presentation"><span  class="active">Principal</span></a>
      <a href="#about">Sobre</a>
      <a href="#services">Serviços</a>
      <a href="#portfolio">Portfolio</a>
      <router-link to="/about">Contato</router-link>
    </div>
  </nav>
  <router-view/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500&display=swap');

*{
  margin: 0px;
  padding: 0px;
  font-family: 'Inter', sans-serif;
  background-color: #1d212a;
  scroll-behavior: smooth;
}

html{
  overflow-x: hidden;
}

#nav-main{
  width: 100%;
  background-color: #1d212a;
  display: flex;
  justify-content: space-around;
  padding: 25px 0px;
  position: fixed;
  z-index: 1000;
  box-shadow: 0px 0px 5px #171718;
}
#logo{
  color: white;
  font-weight: 600;
  font-size: 17px;
  letter-spacing: 3px;
}
#nav-buttons{
  width: 500px;
  display: flex;
  justify-content: space-around;
}
#nav-buttons a{
  color: white;
  text-decoration: none;
  transition: 400ms;
}
#nav-buttons a:hover{
  color:  #05c9d7;
  transition: 400ms;
}
.active{
  color:  #05c9d7;
}

::-webkit-scrollbar {
  width: 10px;
  border-radius: 5px;
}

::-webkit-scrollbar-track {
  background: #373e4e;
  border-radius: 5px;
}

::-webkit-scrollbar-thumb {
  background: rgb(24, 26, 32);
  border-radius: 5px;
}

::-webkit-scrollbar-thumb:hover {
  background: #13171c;
}

::-webkit-scrollbar-thumb:active {
  background: #0b0d0f;
}
</style>