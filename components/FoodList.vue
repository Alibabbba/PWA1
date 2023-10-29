<!-- FoodList.vue -->
<template>
    <div>
      <h3>Food List</h3>
      <p><strong>Total Calories:</strong> {{ totalCalories }}</p>
      <ul>
        <li v-for="food in foodList" :key="food.id">
          {{ food.name }} - {{ food.calories }} calories
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      foodList: Array,
    },
    computed: {
      totalCalories() {
        // Calculate the total calories from the foodList array
        return this.foodList.reduce((total, food) => total + food.calories, 0);
      },
    },
  };
  </script>
  