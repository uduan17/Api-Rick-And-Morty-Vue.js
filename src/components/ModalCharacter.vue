<template>
<!-- Modal --------------------------------------->
<div class="modal fade " id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog ">
    <div class="modal-content">
      <div class="modal-header text-center border border-0">
        <h5 class="card-title "><strong>{{ character.name }}</strong></h5>
        <button type="button" class="btn-close bg-white" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="card mb-3 border border-0" style="max-width: 540px;">
      <div class="row g-0">
       <div class="col-md-4">
      <img :src="character.image" class=" mx-2 img-fluid rounded mt-4" alt="...">
    </div>
    <div class="col-md-4">
      <div class="card-body"> 
        <p class="card-text"><strong class="uno shadow">First seen in</strong> <br>{{ character.originname }}</p>
        <p class="card-text" ><strong class="dos shadow">Last location</strong> <br>{{ character.location }}</p>
      </div>
    </div>
    <div class="col-md-4">
      <div class="card-body">
        <p class="card-text"><strong class="tres shadow">Species</strong> <br>{{ character.species }}</p>
        <p class="card-text"><strong class="cuatro shadow">Status</strong> <br>{{ character.status }}</p>
        <p class="card-text"><strong class="cinco shadow">Gender</strong> <br>{{ character.gender }}</p>
      </div>
    </div>
  </div>
</div>
<div class="modal-footer border border-0">
  <button type="button" class="btn bg-white" data-bs-dismiss="modal">Close</button>
  </div>
</div>
</div>
</div>
</template>
<!-- -------------------------------------- -->
<script>
import axios from "axios";

export default {
  name: 'ModalCharacter',
  props: ["characterId"],
  data() {
    return { character: {}, id: this.characterId };
  },

  created() {
    this.getCharacterId();
  },

  // obtener la data de un personaje
  methods: {
    async getCharacterId() {
      try {
        const { data } = await axios.get(`https://rickandmortyapi.com/api/character/${this.id}`);
        this.character = data;
        this.character.originname = data.origin.name;
        this.character.location = data.location.name;
      } catch (error) {
        console.error(error);
      }
    },
  },
};
</script>
<!-- ------------------------------ -->
<style  scoped>
a{
  cursor: pointer;
}

.card-title{
  background: rgba(16, 15, 15, 0.852);
  border-radius: 8px;
  padding: 3px;
  color: white;
}

.uno{
  background: #839192;
  border-radius: 8px;
  padding: 4px;
  color: white;
}

.dos{
  background: #85C1E9 ;
  border-radius: 8px;
  padding: 3px;
  color: white;
}

.tres{
  background: #F4D03F  ;
  border-radius: 8px;
  padding: 3px;
  color: white;
}

.cuatro{
  background: #EDBB99 ;
  border-radius: 8px;
  padding: 3px;
  color: white;
}

.cinco{
  background: #82E0AA ;
  border-radius: 8px;
  padding: 3px;
  color: white;
}

.modal-content{
  background: #D6EAF8;
}
</style>
