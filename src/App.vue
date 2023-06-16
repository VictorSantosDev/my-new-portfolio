<template>
  <nav id="nav-main">
    <div id="logo">
      Portfolio
    </div>

    <div id="nav-buttons">
      <router-link to="/"> <span  class="active">Principal</span></router-link>
      <router-link to="/about">Sobre</router-link>
      <router-link to="/about">Serviços</router-link>
      <router-link to="/about">Portfolio</router-link>
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

}

#nav-main{
  width: 100%;
  background-color: #1d212a;
  display: flex;
  justify-content: space-around;
  padding: 25px 0px;
  position: fixed;
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
</style>