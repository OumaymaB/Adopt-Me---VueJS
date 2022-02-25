<template>
  <div class="ui four column grid" id="pets">
    <div class="column" v-for="pet in pets" :key="pet.id">
      <Pet
        @add-favorite="$emit('add-favorite', pet.id)"
        @remove-pet="$emit('remove-pet', pet.id)"
        :pet="pet"
      />
    </div>
  </div>
</template>

<script>
import Pet from "./Pet.vue";

export default {
  props: {
    pets: [],
  },
  components: {
    Pet,
  },
  emits: ["remove-pet", "add-favorite"],
};
</script>

<style lang="scss" scoped>
#pets {
  margin: 20px;
}
</style>