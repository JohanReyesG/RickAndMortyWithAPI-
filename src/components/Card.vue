<template>
  <div class="col mt-4">
    <div class="card">
      <div class="card-header">
        
        <img :src="data.image" class="card-img-top image" />
      </div>
      <div class="card-body">
        <h5 class="card-title">{{ data.name }}</h5>
      </div>
      <ul class="list-group list-group-flush">
        <li class="list-group-item"><b>Status: </b>{{ data.status }}</li>
        <li class="list-group-item"><b>Specie: </b>{{ data.species }}</li>
        <li v-if="data.type" class="list-group-item">
          <b>type: </b>{{ data.type }}
        </li>
        <li class="list-group-item"><b>gender: </b>{{ data.gender }}</li>
        <li class="list-group-item"><b>origin: </b>{{ data.origin.name }}</li>
        <li class="list-group-item">
          <b>location: </b>{{ data.location.name }}
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  props: ["data"],
};
</script>
<style lang="css">
.card {
  display: inline-flex;
}
.card-header {
  background: rebeccapurple;
}

.image {
  z-index: 999;
  border-radius: 50%;
}

</style>