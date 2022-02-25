<template>
  <form class="ui form" id="form" @submit.prevent="onSubmit">
    <div class="fields">
      <div class="field">
        <input type="text" placeholder="Name" v-model="name" />
      </div>
      <div class="field">
        <input type="number" placeholder="Age" v-model="age" />
      </div>
      <div class="field">
        <input type="text" placeholder="Image URL" v-model="url" />
      </div>
      <div class="field">
        <button type="submit" class="small ui secondary button">Save</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      age: "",
      url: "",
    };
  },
  methods: {
    onSubmit() {
      const newPet = {
        id: Math.random(),
        name: this.name,
        age: this.age,
        url: this.url,
        isFavorite: false,
      };
      this.$emit("add-pet", newPet);
      this.name = "";
      this.age = "";
      this.url = "";
    },
  },
};
</script>

<style lang="scss" scoped>
#form {
  margin-top: 10px;
  display: flex;
  justify-content: center;
  align-items: center;

  button {
    background-color: aqua;
    color: black;
    border: 3px solid black;
  }
}
</style>