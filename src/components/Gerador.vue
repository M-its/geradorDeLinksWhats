<template>
  <div class="col-12 all-content">
    <header class="col-12 d-flex">
      <!-- logo -->
      <div class="col-12 pt-4 mt-2 align-items-center logo">
        <a href="/">
          <img
            class="col-4"
            src="../../public/img/whatsapp-logo.png"
            alt="Logo Whatsapp"
          />
          <span class="col-8">WhatsApp Link</span>
        </a>
      </div>
    </header>
    <!-- /logo -->

    <div class="col-10 container content-width mt-0 p-5">
      <!-- conteudo -->
      <div class="form-group">
        <label for="">NÚMERO</label>
        <input
          type="text"
          v-model="numero"
          class="form-control"
          placeholder="+55 (21) 00000-0000"
        />
      </div>
      <div class="form-group">
        <label for="">MENSAGEM</label>
        <input
          type="text"
          v-model="mensagem"
          class="form-control"
          placeholder="Olá, acessei seu WhatsLink"
        />
      </div>
      <div class="">
        <button
          @click="Geralink()"
          class="btn btn-outline-success btn-lg btn-block"
        >
          GERAR LINK
        </button>
      </div>
    </div>
    <!-- conteudo -->
    <div class="col-10 container content-width">
      <div class="row d-flex justify-content-between flex-wrap">
        <div class="col-md-6 list d-flex">
          <ol>
            <li>Insira o nº do WhatsApp Ex: 55 21 9 0000-0000</li>
            <li>Escreva a mensagem padrão que será exibida</li>
            <li>Clique em “GERAR LINK”</li>
            <li>Copie o link e compartilhe</li>
            <li>Antes de usar, faça o teste</li>
          </ol>
        </div>
        <div class="col-md-5 mesage">
          <p>
            Crie um Link Direto<br />
            <span class="strong-text">Para seu WhatsApp</span><br />
            Rápido, Fácil e Grátis!
          </p>
        </div>
      </div>
    </div>
    <div class="col-10 description container content-width">
      O gerador de links para o WhatsApp é uma ótima ferramenta para ações de
      marketing ou relacionamento. Com o link para mensagens personalizadas do
      WhatsApp, você poderá utilizar em campanhas, redes sociais, email
      marketing, banners e etc. O bom de encurtar e personalizar links e
      mensagens do WhatsApp é que funcionará no desktop e no mobile da mesma
      forma. Faça bom uso da ferramenta encurtadora de WhatsApp.
    </div>
  </div>
</template>

<script>
export default {
  name: "Gerador",
  data: function() {
    return {
      numero: "",
      mensagem: "",
      url: "",
    };
  },
  methods: {
    Geralink: function() {
      let n = this.numero.replace(/[^0-9]/g, "");
      let m = encodeURI(this.mensagem);
      this.url = `https://api.whatsapp.com/send?phone=${n}&text=${m}`;
      this.$router.push({
        name: "Resultado",
        params: {
          link: this.url,
        },
      });
    },
  },
};
</script>
<style scoped>
a:link {
  text-decoration: none;
}
a:visited {
  text-decoration: none;
}
a:hover {
  text-decoration: none;
}
a:active {
  text-decoration: none;
}
.all-content {
  padding-right: 0px;
  padding-left: 0px;
}
.content-width {
  background: white;
  max-width: 900px;
}
header {
  background: #075e54;
  height: 120px;
  padding-right: -15px;
  padding-left: -15px;
}
.logo span {
  color: white;
  font-size: 3em;
  line-height: 1.6em;
  margin-left: 15px;
  padding: 15px 15px 15px 0px;
}
img {
  padding-bottom: 35px;
  width: 80px;
}
.logo {
  margin-left: auto;
  margin-right: auto;
  padding: 20px;
}
.container {
  margin-top: 20px;
}
ol {
  list-style: none;
  counter-reset: li;
}
li::before {
  content: counter(li);
  color: #075e54;
  display: inline-block;
  width: 1em;
  margin-left: -1em;
  font-size: 1.3em;
}
li {
  counter-increment: li;
}
.mesage {
  margin-top: 50px;
}
.list {
  margin-top: 50px;
  padding-left: 20px;
  margin-left: 20px;
  color: #808080;
  font-size: 1.15em;
  font-weight: 300;
  list-style: #075e54;
}
p {
  font-size: 1.3em;
  font-weight: 500;
}
span.strong-text {
  color: #075e54;
  font-weight: 900;
  font-size: 1.6em;
  text-align: end;
}
.description {
  color: #aaaaaa;
  margin-top: 150px;
}

/* extra small devices (landscape phones, 576px and up) */
@media (min-width: 200px) and (max-width: 479.98px) {
  .logo {
    margin-left: 40px;
  }
  img {
    width: 40px;
    margin-top: 20px;
    padding-right: 0px;
  }
  .logo span {
    color: white;
    font-size: 1.3em;
    line-height: 1em;
  }
  .list {
    margin: 20px 20px 20px 0px;
    font-size: 1em;
  }
  .mesage {
    margin-top: 50px;
    text-align: center;
  }
  .description {
    margin-top: 70px;
    margin-bottom: 50px;
  }
}

/* small devices (landscape phones, 576px and up) */
@media (min-width: 480px) and (max-width: 767.98px) {
  img {
    margin-top: 10px;
    width: 60px;
    padding-bottom: 35px;
    padding-right: 0px;
  }
  .logo span {
    color: white;
    font-size: 2.5em;
    line-height: 0.6em;
  }
  .list {
    margin-top: 20px;
  }
  .mesage {
    margin-top: 100px;
    text-align: center;
  }
  .description {
    color: #aaaaaa;
    margin-top: 130px;
    margin-bottom: 50px;
  }
}

/* Medium devices (tablets, 768px and up) */
@media (min-width: 768px) and (max-width: 991.98px) {
  .logo {
    max-width: 900px;
  }
  .description {
    color: #aaaaaa;
    margin-top: 150px;
    margin-bottom: 50px;
  }
}

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) and (max-width: 1199.98px) {
  .logo {
    max-width: 900px;
  }
  button {
    width: 300px;
    margin-left: auto;
  }
}

/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {
  .logo {
    max-width: 900px;
  }
  button {
    width: 300px;
    margin-left: auto;
  }
}
</style>
