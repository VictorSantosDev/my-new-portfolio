<template>
  <div id="container-home">
    <div class="presentation">
      <div class="box-msg-presentation">
        <p class="msg-presentation">Olá, eu me chamo</p>
        <p class="msg-my-name">Victor Emanuel</p>
        <p class="msg-about">
          E sou <span style="color: #05c9d7; font-weight: 600;">Desenvolvedor Back-End PHP</span>
        </p>
        <div class="msg-plus-about">
          <p>
            Fique à vontade para dar uma olhada nas minhas redes sociais, 
          </p>
          <p>
            mas se preferir, pode explorar o meu portfólio por aqui.
          </p>
        </div>
        <div class="social-media">
            <mdicon name="whatsapp" class="icon-social-media" style="color: #05c9d7;" :size="20"/>
            <mdicon name="facebook" class="icon-social-media" style="color: #05c9d7;" :size="20"/>
            <mdicon name="instagram" class="icon-social-media" style="color: #05c9d7;" :size="20"/>
            <mdicon name="linkedin" class="icon-social-media" style="color: #05c9d7;" :size="20"/>
        </div>
        <div class="box-button-cv">
          <button class="btn-cv">Baixar CV</button>
        </div>
      </div>
      <div class="box-my-self">
        <img class="img-my-self" :src="imagePath" alt="Imagem" />
      </div>
    </div>
  </div>
</template>

<script>

import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data(){
    return {
      imagePath: 'img/my-self-1.png'
    };
  }
}
</script>

<style scoped>
#container-home{
  padding-top: 70px;
  color: white;
  height: calc(100vh - 70px);
}
.presentation{
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 100%;
}
.img-my-self{
  width: 400px;
}
.msg-presentation{
  font-size: 35px;
  margin-bottom: 5px;
  font-weight: 500;
}
.msg-my-name{
  font-size: 50px;
  margin-bottom: 5px;
  font-weight: 600;
}
.msg-about{
  font-size: 30px;
  margin-bottom: 5px;
  font-weight: 500;
  margin-bottom: 20px;
}
.msg-plus-about{
  margin-bottom: 30px;
}

.social-media{
  display: flex;
  margin-bottom: 30px;
}

.icon-social-media{
  border: 1px solid #05c9d7;
  border-radius: 50%;
  padding: 8px;
  margin-right: 15px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition: 400ms;
}
.icon-social-media svg:hover, .icon-social-media:hover{
  box-shadow: 0px 2px 5px #05c9d7;
  transform: translate(0px, -10px);
  transition: 400ms;
}

.btn-cv{
  border: none;
  background-color: #05c9d7;
  margin: 0px;
  padding: 10px 30px;
  border-radius: 20px;
  cursor: pointer;
  box-shadow: 0 0px 10px#05c9d7;
  transition: 400ms;
  font-weight: 500;
}

.btn-cv:hover{
  box-shadow: 0 0px 0px#05c9d7;
}

/* .box-my-self{
  border: 1px solid red;
} */
.img-my-self{
  animation: float 4s ease-in-out infinite;
  background: transparent;
}
@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-05%);
  }
}
</style>