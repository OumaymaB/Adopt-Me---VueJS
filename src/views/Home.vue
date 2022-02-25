<template>
  <FormPet @add-pet="addPet" />
  <Pets @remove-pet="removePet" :pets="pets" @add-favorite="addFavorite" />
</template>

<script>
import Pets from "../components/Pets.vue";
import FormPet from "../components/FormPet.vue";
export default {
  name: "Home",
  data() {
    return {
      pets: [],
    };
  },
  components: {
    Pets,
    FormPet,
  },
  methods: {
    addPet(pet) {
      this.pets = [...this.pets, pet];
    },
    removePet(id) {
      if (confirm("Are you sure you want to remove it ?")) {
        console.log(id + "home");
        this.pets = this.pets.filter((pet) => pet.id != id);
      }
    },

    addFavorite(id) {
      this.pets = this.pets.map((pet) =>
        pet.id === id ? { ...pet, isFavourite: !pet.isFavourite } : pet
      );
    },
  },
  created() {
    this.pets = [
      {
        id: 1,
        name: "dog",
        age: 2,
        isFavourite: true,
      },
      {
        id: 2,
        name: "dog",
        age: 2,
        isFavourite: true,
      },
      {
        id: 3,
        name: "dog",
        age: 2,
        isFavourite: true,
      },
      {
        id: 4,
        name: "dog",
        age: 2,
        isFavourite: true,
      },
      {
        id: 5,
        name: "dog",
        age: 2,
        isFavourite: false,
      },
    ];
  },
};
</script>
