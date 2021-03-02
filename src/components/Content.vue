<template>
  <div>
    <div class="row myform">
      <div class="col mt-4">
        <div class="form-group">
          <label>Name</label>
          <input
            type="text"
            placeholder="Name"
            class="form-control"
            v-model="name"
            @keyup="getData()"
          />
        </div>
      </div>
      <div class="col mt-4">
        <div class="form-group">
          <label>Specie</label>
          <input
            type="text"
            placeholder="Specie"
            class="form-control"
            v-model="specie"
            @keyup="getData()"
          />
        </div>
      </div>
      <div class="col mt-4">
        <div class="form-group">
          <label>status</label>
          <select class="form-control" v-model="status" @click="getData()">
            <option value="">All</option>
            <option value="alive">Alive</option>
            <option value="dead">Dead</option>
            <option value="unknown">Unknown</option>
          </select>
        </div>
      </div>
      <div class="col mt-4">
        <div class="form-group">
          <label>Gender</label>
          <select class="form-control" v-model="gender" @click="getData()">
            <option value="">All</option>
            <option value="female">Female</option>
            <option value="male">Male</option>
            <option value="genderless">genderless</option>
            <option value="unknown">Unknown</option>
          </select>
        </div>
      </div>
    </div>
    <div
    style="min-height:100vh;"
      class="row justify-content-center row-cols-sm-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5"
    >
      <Card  v-for="item in data" :key="item.id" :data="item"  />
      <h3 v-if="data == undefined">No information available from the given filters</h3>
    </div>
    <nav v-if="data != undefined" aria-label="Page navigation example">
      <ul class="pagination justify-content-center">
        <li class="page-item">
          <a class="page-link" tabindex="-1" @click="getData(info.prev)">
            Previous</a
          >
        </li>
      
        <li class="page-item">
          <a class="page-link" @click="getData(info.next)">Next</a>
        </li>
      </ul>
    </nav>
  </div>
</template>
<script>
import Card from "./Card";
export default {
  components: {
    Card,
  },
  data() {
    return {
      name: "",
      status: "",
      specie: "",
      gender: "",
      data: [],
      page: 1,
      info: {
        count: 0,
        pages: 0,
        next: "",
        prev: "",
      },
      url: "",
    };
  },
  created() {
    this.getData();
  },
  methods: {
    
    async getData(newurl) {
      const api =
        "https://rickandmortyapi.com/api/character/?page=1&name=" +
        this.name +
        "&status=" +
        this.status +
        "&species=" +
        this.specie +
        "&gender=" +
        this.gender;
      if (!newurl) {
        this.url = api;
        const response = await fetch(this.url);
        const json = await response.json();
        this.data = json.results;
        this.info = json.info;
      } else {
        this.url = newurl;
        const response = await fetch(
          this.url +
            "&name=" +
            this.name +
            "&status=" +
            this.status +
            "&species=" +
            this.specie +
            "&gender=" +
            this.gender
        );
        const json = await response.json();
        this.data = json.results;
        this.info = json.info;
      }

      this.url = "";
    },
  },
};
</script>