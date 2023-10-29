<template>
    <div class="exercise-input">
      <h2>Enter Your Exercise</h2>
      <input v-model="exerciseName" placeholder="Exercise Name">
      <input v-model="caloriesBurned" type="number" placeholder="Calories Burned">
      <button @click="addExercise">Add</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        exerciseName: '',
        caloriesBurned: '',
      };
    },
    methods: {
      addExercise() {
        // Implement logic to add the entered exercise data
        const exerciseItem = {
          name: this.exerciseName,
          caloriesBurned: parseFloat(this.caloriesBurned),
        };
  
        // You can emit an event to notify the parent component about the added exercise item.
        this.$emit('exercise-added', exerciseItem);
  
        // Clear the input fields
        this.exerciseName = '';
        this.caloriesBurned = '';
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add styling for the exercise input component */
  .exercise-input {
    margin: 20px 0;
  }
  </style>
  