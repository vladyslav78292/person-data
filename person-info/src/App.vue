<script>
  export default {
    data() {
      return {
        person: [],
        isAccesOpen: false,
      };
    },

    created() {
      fetch("https://swapi.dev/api/people/1/")
        .then((response) => response.json())
        .then((data) => {
          this.person = data;
        })
        .catch ((error) => console.log(error))
    }
  }
</script>

<template>
  <div class="button-container">
    <button @click="isAccesOpen = true"  class="button-get-info">Click me to get info</button>
  </div>
  <div v-if="isAccesOpen" class="person-info">
    <p class="person person-name" >Name: {{ person.name }}</p>
    <p class="person person-height" >Height: {{ person.height }} cm</p>
    <p class="person person-mass" >Mass: {{ person.mass }} kg</p>
    <p class="person person-hair-c" >Hair color: {{ person.hair_color }}</p>
    <p class="person person-skin-c" >Skin color: {{ person.skin_color }}</p>
    <p class="person person-eyes-c" >Eyes color: {{ person.eye_color }}</p>
    <p class="person person-brirth" >Birth year: {{ person.birth_year }}</p>
    <p class="person person-gender" >Gender: {{ person.gender }}</p>
    <p class="person person-films" >Amout of films: {{ person.films.length }}</p>
  </div>
</template>

<style>
  body {
  box-sizing: border-box;
  }

  .button-container {
    display: flex;
    justify-content: center;
  }

  .button-get-info {
    background-color:aquamarine;
    border: none;
    color: darkmagenta;
    font-weight: 700;
    font-size: 40px;
    padding: 20px;
    margin-top: 120px;
    border-radius: 40px;
  }

  .person-info {
    display: flex;
    flex-direction: column;
    font-size: 24px;
    margin-top: 90px;
  }

  .person {
    display: flex;
    justify-content: center;
  }
</style>
