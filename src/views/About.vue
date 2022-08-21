<template>
  <div class="about">
    <h1>Статистика</h1>
  </div>
  <div class="count">
    <h4>Количество планет:</h4>
    <ul>
      <li v-for="(planet, index ) in planets"
      :key="index">
        {{ planet.count }}
      </li>
    </ul>
  </div>
  <div class="count">
    <h4>Количество персонажей:</h4>
    <ul>
      <li v-for="(people, index ) in peoples"
          :key="index">
        {{ people.count }}
      </li>
    </ul>
  </div>
  <div class="count">
    <h4>Количество кораблей:</h4>
    <ul>
      <li v-for="(ship, index ) in ships"
          :key="index">
        {{ ship.count }}
      </li>
    </ul>
  </div>
  <div class="count">
    <h4>Фильмы:</h4>
    <ul>
      <li v-for="(film, index ) in films"
          :key="index">
        {{ film.count }}
      </li>
    </ul>
  </div>
  <div class="count">
    <h4>Средства передвижения:</h4>
    <ul>
      <li v-for="(vehicle, index ) in vehicles"
          :key="index">
        {{ vehicle.count }}
      </li>
    </ul>
  </div>
  <div class="count">
    <h4>Средства:</h4>
    <ul>
      <li v-for="(spec, index ) in species"
          :key="index">
        {{ spec.count }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

  export  default {
     data () {
       return {
         planets: null,
         peoples: null,
         ships: null,
         films: null,
         vehicles: null,
         species: null
       }
     },
    mounted() {
      axios
          .get('https://swapi.dev/api/planets/')
          .then(response => (this.planets = response));
      axios
          .get('https://swapi.dev/api/people/')
          .then(response => (this.peoples = response));
      axios
          .get('https://swapi.dev/api/starships/')
          .then(response => (this.ships = response));
      axios
          .get('https://swapi.dev/api/films/')
          .then(response => (this.films = response));
      axios
          .get('https://swapi.dev/api/vehicles/')
          .then(response => (this.vehicles = response));
      axios
          .get('https://swapi.dev/api/species/')
          .then(response => (this.species = response));

    }
  }

</script>

<style>
  li {
    list-style: none;
  }
  .count {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }
</style>