<template>
  <div>
    <h3>Exercise List</h3>
    <p><strong>Total Calories:</strong> {{ totalExerciseCalories }}</p>
    <ul>
      <li v-for="exercise in exerciseList" :key="exercise.id">
        {{ exercise.name }} - {{ exercise.caloriesBurned }} calories burned
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    exerciseList: Array,
  },
  computed: {
    totalExerciseCalories() {
      // Calculate the total calories from the exerciseList array
      return this.exerciseList.reduce((total, exercise) => total + parseFloat(exercise.caloriesBurned), 0);
    },
  },
};
</script>
