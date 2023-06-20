<template>
  <div id="container-home">
    <div id="presentation" class="presentation">
      <div 
      v-motion
      :initial="{ opacity: 0, x: -100 }"
      :enter="{ opacity: 1, x: 0 }"
      :variants="{ custom: { x: -100 } }"
      :delay="200"
      class="box-msg-presentation">
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
            <a :href="urlWhatsapp" target="_blank">
              <mdicon name="whatsapp" class="icon-social-media" style="color: #05c9d7;" :size="20"/>
            </a>
            <a :href="urlFacebook" target="_blank">
              <mdicon name="facebook" class="icon-social-media" style="color: #05c9d7;" :size="20"/>
            </a>
            <a :href="urlInstagram" target="_blank">
              <mdicon name="instagram" class="icon-social-media" style="color: #05c9d7;" :size="20"/>
            </a>
            <a :href="urlLinkedin" target="_blank">
              <mdicon name="linkedin" class="icon-social-media" style="color: #05c9d7;" :size="20"/>
            </a>
        </div>
        <div class="box-button-cv">
          <a :href="pathCv" download="curriculo-victor.pdf" class="btn-cv">Baixar CV</a>
        </div>
      </div>
      <div 
      v-motion
      :initial="{ opacity: 0, x: 100 }"
      :enter="{ opacity: 1, x: 0 }"
      :variants="{ custom: { x: -100 } }"
      :delay="300"
      class="box-my-self">
        <img class="img-my-self" :src="imagePath" alt="Imagem" />
      </div>
    </div>
    <div id="about" class="box-about">
      <div 
      v-motion
      :initial="{ opacity: 0, x: 100 }"
      :enter="{ opacity: 1, x: 0 }"
      :variants="{ custom: { x: -100 } }"
      :delay="300"
      when: false
      class="box-my-self">
        <img class="img-abou-my-self" :src="imagePath" alt="Imagem" />
      </div>
      <div v-motion-slide-visible-left class="box-msg-about">
        <p class="title-about">
          Sobre <span style="color: #05c9d7;">Mim</span>
        </p>
        <p class="my-job">
          Desenvolvedor Back-End
        </p>
        <p>
          Olá, meu nome é Victor Emanule Almeida Santos e tenho {{ myAge }},
          sou desenvolvedor back-end e estudande de Analise e desenvolvimento de sistemas
          na universidade Nove de Julho(UNINOVE). 
        </p>
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
      imagePath: 'img/my-self-1.png',
      urlWhatsapp: 'https://api.whatsapp.com/send?phone=5511964780920&text=Oi%20Victor%20tudo%20bem%20?%20',
      urlFacebook: 'https://www.facebook.com/profile.php?id=100023911251147',
      urlInstagram: 'https://www.instagram.com/victor_sannttoss/',
      urlLinkedin: 'https://www.linkedin.com/in/victor-e-2b8452a7/',
      pathCv: '@/assets/2023-cv.pdf',
      myAge: '0'
    };
  },
  methods: {
  },
  mounted(){
      const today = new Date();
      const birthDate = new Date('1999-08-19');
      let age = today.getFullYear() - birthDate.getFullYear();
      const m = today.getMonth() - birthDate.getMonth();

      if (m < 0 || (m === 0 && today.getDate() < birthDate.getDate())) {
          age--;
      }

      this.myAge = age;
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
.box-about{
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 100%;
}
.img-my-self{
  width: 400px;
}
.img-abou-my-self{
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
  color: #000000;
  font-size: 12px;
  text-decoration: none;
}

.btn-cv:hover{
  box-shadow: 0 0px 0px#05c9d7;
  color: #ffffff;
}

.box-msg-about{
  width: 500px;
}

.title-about{
  font-size: 25px;
  font-weight: 500;
  margin-bottom: 10px;
}

/** my-job*/

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