<template>
  <div class="cards">
    <div class="card" v-for="(planet, index) in planets" :key="index">
      <div> Имя планеты: {{planet.name}} </div>
      <div class="description" v-if="isVisible">
        <p>Диаметр: {{planet.diameter}}</p>
        <p>Климат: {{ planet.climate}}</p>
        <p>Население: {{ planet.population}}</p>
      </div>
      <button class="button" @click="toggleElement">показать\скрыть</button>
    </div>
    <div class="card" v-for="(planet, index) in planets2" :key="index">
      <div> Имя планеты: {{planet.name}} </div>
      <div class="description" v-if="isVisible2">
        <p>Диаметр: {{planet.diameter}}</p>
        <p>Климат: {{ planet.climate}}</p>
        <p>Население: {{ planet.population}}</p>
      </div>
      <button class="button" @click="toggleElement2">показать\скрыть</button>
    </div>
    <div class="card" v-for="(planet, index) in planets3" :key="index">
      <div> Имя планеты: {{planet.name}} </div>
      <div class="description" v-if="isVisible3">
        <p>Диаметр: {{planet.diameter}}</p>
        <p>Климат: {{ planet.climate}}</p>
        <p>Население: {{ planet.population}}</p>
      </div>
      <button class="button" @click="toggleElement3">показать\скрыть</button>
    </div>
    <div class="card" v-for="(planet, index) in planets4" :key="index">
      <div> Имя планеты: {{planet.name}} </div>
      <div class="description" v-if="isVisible4">
        <p>Диаметр: {{planet.diameter}}</p>
        <p>Климат: {{ planet.climate}}</p>
        <p>Население: {{ planet.population}}</p>
      </div>
      <button class="button" @click="toggleElement4">показать\скрыть</button>
    </div>
    <div class="card" v-for="(planet, index) in planets5" :key="index">
      <div> Имя планеты: {{planet.name}} </div>
      <div class="description" v-if="isVisible5">
        <p>Диаметр: {{planet.diameter}}</p>
        <p>Климат: {{ planet.climate}}</p>
        <p>Население: {{ planet.population}}</p>
      </div>
      <button class="button" @click="toggleElement5">показать\скрыть</button>
    </div>
    <div class="card" v-for="(planet, index) in planets6" :key="index">
      <div> Имя планеты: {{planet.name}} </div>
      <div class="description" v-if="isVisible6">
        <p>Диаметр: {{planet.diameter}}</p>
        <p>Климат: {{ planet.climate}}</p>
        <p>Население: {{ planet.population}}</p>
      </div>
      <button class="button" @click="toggleElement6">показать\скрыть</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data: () => ({
    planets: {
    },
    planets2: {
    },
    planets3: {
    },
    planets4: {
    },
    planets5: {
    },
    planets6: {
    },
    isVisible: false,
    isVisible2: false,
    isVisible3: false,
    isVisible4: false,
    isVisible5: false,
    isVisible6: false
  }),
  methods: {
    async getPlanet() {
      const res = await axios.get('https://swapi.dev/api/planets/1');
      this.planets = [res.data];
    },
    async getPlanet2() {
      const res = await axios.get('https://swapi.dev/api/planets/2');
      this.planets2 = [res.data];
    },
    async getPlanet3() {
      const res = await axios.get('https://swapi.dev/api/planets/3');
      this.planets3 = [res.data];
    },
    async getPlanet4() {
      const res = await axios.get('https://swapi.dev/api/planets/4');
      this.planets4 = [res.data];
    },
    async getPlanet5() {
      const res = await axios.get('https://swapi.dev/api/planets/5');
      this.planets5 = [res.data];
    },
    async getPlanet6() {
      const res = await axios.get('https://swapi.dev/api/planets/6');
      this.planets6 = [res.data];
    },
    toggleElement() {
      this.isVisible = !this.isVisible;
    },
    toggleElement2() {
      this.isVisible2 = !this.isVisible2;
    },
    toggleElement3() {
      this.isVisible3 = !this.isVisible3;
    },
    toggleElement4() {
      this.isVisible4 = !this.isVisible4;
    },
    toggleElement5() {
      this.isVisible5 = !this.isVisible5;
    },
    toggleElement6() {
      this.isVisible6 = !this.isVisible6;
    }
  },
  created() {
    this.getPlanet();
    this.getPlanet2();
    this.getPlanet3();
    this.getPlanet4();
    this.getPlanet5();
    this.getPlanet6();
  },
};
</script>

<style>
  .cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 25px;
    margin: 0 auto;
    max-width: 80%;
  }

  .card {
    border: 1px solid black;
    margin: 0 20px;
  }

  .button {
    margin-top: 12px;
    padding: 7px;
    border-radius: 8px;
    border: 0;
  }

  .button:hover {
    background-color:  goldenrod;
    color: #FFFFFF;
  }
  
  @media screen  and  (max-width: 767px){
     .cards {
       grid-template-columns: repeat(2, 1fr);
     }
  }

  @media screen  and  (max-width: 500px){
    .cards {
      grid-template-columns: repeat(1, 1fr);
    }
  }
</style>