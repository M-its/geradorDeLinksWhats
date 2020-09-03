<template>
  <div class="everything">
    <Gerador />
  </div>
</template>

<script>
// @ is an alias to /src
import Gerador from "@/components/Gerador.vue";

export default {
  name: "Home",
  components: {
    Gerador
  }
};
</script>
<style scoped>
.everything {
  max-width: 100vw;
}
</style>
