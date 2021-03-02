<template>
  <div class="home">
    <div  class="container-fluid mb-4">
      <Content />
    </div>
    <div style="min-height:auto;" class="navbar relative-bottom navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#"> Rick <span>And</span> Morty </a>
        <p>
          Data from:
          <a href="https://rickandmortyapi.com/"
            >https://rickandmortyapi.com/</a
          >
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Content from "@/components/Content.vue";

@Component({
  components: {
    Content,
  },
})
export default class Home extends Vue {}
</script>

<style lang="css">
  .home{
    background:#152933;
  }
  label{
    color: #fff;
  }
</style>