<template>
  <div class="container">
    <div class="row">
      <div class="col-10 container label-link">
        <div class="form-group">
          <label for="exampleControlTextarea1">SEU LINK FOI GERADO</label>
          <textarea
            class="form-control"
            id="url"
            rows="3"
            v-model="$route.params.link"
          ></textarea>
        </div>
        <div class="col-12 d-flex  justify-content-end buttons">
          <button
            id="copiar"
            data-clipboard-target="#url"
            class="btn btn-success btn-md margem"
          >
            COPIAR
          </button>
          <a
            target="_black"
            :href="$route.params.link"
            class="btn btn-outline-info btn-md margem"
          >
            TESTAR
          </a>
          <router-link to="/" class="btn btn-outline-dark btn-md" btn-md
            >VOLTAR</router-link
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ClipboardJS from "clipboard";
new ClipboardJS("#copiar");
export default {};
</script>
<style scoped>
textarea {
  resize: none;
}
.buttons {
  padding-right: 0;
}
.margem {
  margin-right: 25px;
}
.label-link {
  margin-top: 20px;
}
</style>
