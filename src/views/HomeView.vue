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
        <p class="text-about">
          Olá, meu nome é Victor Emanuel Almeida Santos e tenho {{ myAge }}, anos. 
          Sou desenvolvedor back-end e estudante de Análise e Desenvolvimento de 
          Sistemas na Universidade Nove de Julho (UNINOVE).
        </p>
      </div>
    </div>
    <div id="services">
    </div>
    <div id="portfolio">
      <div>
        <div class="box-title-portfolio">
          <span v-motion-slide-visible-top class="title-porfolio">
            Últimos <span style="color: #05c9d7;">Projetos</span>
          </span>
        </div>
        <div v-motion-slide-visible-once-top class="box-card-portfolio">
          <CardProject />
          <CardProject />
          <CardProject />
        </div>
      </div>
    </div>
    <div v-motion-slide-visible-top :delay="200" id="contact">
      <div class="title-contact">
        <span>Entre em <span style="color: #05c9d7;">Contato</span></span>
      </div>
      <form class="box-form">
        <div class="inputs-1">
          <input type="text" class="input-1-name-complete" placeholder="Nome Completo">
          <input type="text" class="input-1-address-email" placeholder="Endereço de E-mail">
        </div>
        <div class="inputs-2">
          <input type="text" class="input-2-mobile-numebr" placeholder="Telefone para Contato">
          <input type="text" class="input-2-address-email" placeholder="Assunto do E-mail">
        </div>
        <div class="textarea-box">
          <textarea name="" id="" placeholder="Sua Mensagem"></textarea>
        </div>
      </form>
    </div>
    <footer class="footer">
    </footer>
  </div>
</template>

<script>

import CardProject from '@/components/CardProject.vue';

export default {
  name: 'HomeView',
  components: {
    CardProject
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
.presentation, .box-about {
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
  font-size: 14px;
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
  font-size: 30px;
  font-weight: 900;
  margin-bottom: 5px;
}

.my-job{
  font-size: 20px;
  font-weight: 900;
  margin-bottom: 25px;
}

.text-about{
  font-size: 14px;
}

#portfolio{
  display: flex;
  flex-direction: column;
  margin: 80px;
  height: 100%;
}
.box-card-portfolio{
  display: flex;
  padding: 0px 20px;
  width: 100%;
  justify-content: space-around;
}

.box-title-portfolio{
  text-align: center;
  margin: 30px;
}

.title-porfolio{
  font-size: 30px;
  font-weight: 600;
}

#contact{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.title-contact{
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}

.title-contact span{
  font-weight: 600;
  font-size: 30px;
}

.box-form{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  box-sizing: border-box;
}

.input-1-name-complete,
.input-1-address-email,
.input-2-mobile-numebr,
.input-2-address-email{
  width: 300px;
  height: 50px;
  padding-left: 10px;
  font-size: 0.8em;
  margin: 5px;
  border: none;
  background: #363d4e;
  border-radius: 8px;
  color: #ffffff;
}

.textarea-box{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.textarea-box textarea{
  resize: none;
  padding: 10px;
  font-size: 0.8em;
  border: none;
  background: #363d4e;
  border-radius: 8px;
  margin: 5px;
  width: 100%;
  height: 200px;
  color: #ffffff;
}

/* .box-my-self{
  border: 1px solid red;
} */

.footer{
  height: 100px;
  width: 100%;
}

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

textarea:focus, input:focus, select:focus {
    box-shadow: 0 0 0 0;
    border: 0 none;
    outline: 0;
} 
</style>