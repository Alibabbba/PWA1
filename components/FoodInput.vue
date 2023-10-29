<template>
  <div class="food-input">
    <h2>Co dziś jadłeś?</h2>
    <input v-model="foodName" placeholder="Food Name">
    <input v-model="calories" type="number" placeholder="Calories">
    <button @click="addFood">Dodaj</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      foodName: '',
      calories: '',
    };
  },
  methods: {
    addFood() {
      // Implement logic to add the entered food and calories data
      const foodItem = {
        name: this.foodName,
        calories: parseFloat(this.calories),
      };

      // You can emit an event to notify the parent component about the added food item.
      this.$emit('food-added', foodItem);

      // Clear the input fields
      this.foodName = '';
      this.calories = '';
    },
  },
};
</script>

<style scoped>
/* Add styling for the food input component */
.food-input {
  margin: 20px 0;
}
</style>
