<template>
  <div class="ui card">
    <div class="image"><img src="pet.url" alt="pet" /></div>
    <div class="content">
      <a class="header">Name : {{ pet.name }}</a>
      <div class="description">Age : {{ pet.age }}</div>
    </div>
    <div class="B">
      <div>
        <i
          @click="$emit('add-favorite', pet.id)"
          :class="[
            pet.isFavourite ? 'big heart icon' : 'big heart outline icon',
          ]"
        ></i>
      </div>
      <button @click="onRemove(pet.id)" class="small ui red button">
        Remove X
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    pet: Object,
  },
  methods: {
    onRemove(id) {
      this.$emit("remove-pet", id);
    },
  },
};
</script>

<style lang="scss" scoped>
.B {
  display: flex;
  justify-content: space-between;
  margin: 20px;
}
</style>