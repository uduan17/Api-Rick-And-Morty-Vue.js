<template>
  <div class="container d-flex justify-content-center flex-wrap">
    <div class="card mx-3 mt-4 shadow"
      style="width: 18rem" v-for="(character, index) in characters" :key="index">
        <a @click="showCharacterModal(character.id)">
          <img :src="character.image" class="card-img-top"  alt="" />
        </a>
        <h5 class="rounded-bottom">{{ character.name }} </h5>
    </div>
    <!-- Modal -->
    <div v-if="load"><ModalCharacter :characterId="characterId" /></div>
  </div>
  <br/>
</template>
  
<script>
import axios from "axios";
import ModalCharacter from "./ModalCharacter.vue";
import * as bootstrap from "bootstrap";

export default {
  name: "AllCharacters",
  components: {
    ModalCharacter,
  },

  data() {
    return {
      characters: null,
      characterId: "",
      load: false,
      modal: null,
    };
  },

  mounted() {
    this.getAllCharacters();
  },

// Obtener la data de los personajes
  methods: {
    async getAllCharacters() {
      const response = await axios.get(
        "https://rickandmortyapi.com/api/character"
      );
      this.characters = response.data.results;
    },

    // funcion que llama al modal
    showCharacterModal(id) {
      this.load = true;
      this.mostrarModal();
      this.characterId = id;
    },

    // mostrar modal
    mostrarModal() {
      this.load = true;
      setTimeout(() => {
        this.modal = new bootstrap.Modal(
          document.getElementById("exampleModal"),
          { keyboard: false }
        );

        this.modal.show();
        const modal = document.getElementById("exampleModal");
        modal.addEventListener("hidden.bs.modal", () => {
          this.load = false;
        });
      }, 200);
    },
    // Cerrar modal
    ocultarModal() {
      this.modal.hide();
    },
  },
};
</script>
  
  <style scoped>
.active {
  border-radius: 50px;
  background: green;
}

a {
  cursor: pointer;
}

.card:hover {
  transform: scale(1.07);
}
.card {
  border: 0;
  --bs-card-title-spacer-y: 0;
  transition: transform 0.5s;
}

h5{
  background-color: #F39C12;
  padding: 5px;
  font-weight: bold;
  color: white;
  margin-bottom: -0.5rem
}

</style>