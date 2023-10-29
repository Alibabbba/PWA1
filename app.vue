<template>
  <div>
    <Header />
    <div class="input-container">
      <div class="input-section">
        <FoodInput @food-added="handleFoodAdded" />
        <FoodList :foodList="foodList" />
      </div>
      <div class="input-section">
        <ExerciseInput @exercise-added="handleExerciseAdded" />
        <ExerciseList :exerciseList="exerciseList" />
      </div>
    </div>
    <div class="total-calories">
          <h3>Total Calories: {{ totalCalories }}</h3>
    </div>

    <Calendar />
    <div>
      <h1>Kalendarz</h1>
      <Calendar :year="2023" :month="10" /> <!-- Przykład przekazywania danych wejściowych -->
    </div>
    <MessageBox />
    <!-- Other components go here -->
  </div>
</template>

<script>
import Calendar from '~/components/Calendar.vue';
import Header from '~/components/Header.vue';
import MessageBox from '~/components/MessageBox.vue';
import FoodInput from '~/components/FoodInput.vue';
import FoodList from '~/components/FoodList.vue';
import ExerciseInput from '~/components/ExerciseInput.vue';
import ExerciseList from '~/components/ExerciseList.vue';

export default {
  components: {
    Calendar,
    Header,
    MessageBox,
    FoodInput,
    FoodList,
    ExerciseInput,
    ExerciseList,
    // Add other components here
  },
  data() {
    return {
      year: new Date().getFullYear(),
      month: new Date().getMonth(),
      foodList: [],
      exerciseList: [], // Add an array for exercise items
    };
  },
  computed: {
    totalCalories() {
      const foodCalories = this.foodList.reduce((total, food) => total + parseFloat(food.calories), 0);
      const exerciseCalories = this.exerciseList.reduce((total, exercise) => total + parseFloat(exercise.caloriesBurned), 0);
      return foodCalories - exerciseCalories;
    },
  },
  methods: {
    handleFoodAdded(foodItem) {
      foodItem.id = Date.now();
      this.foodList.push(foodItem);
    },
    handleExerciseAdded(exerciseItem) {
      exerciseItem.id = Date.now();
      this.exerciseList.push(exerciseItem);
    },
  },
};
</script>

<style scoped>
  /* Add styling for the layout */
  .input-container {
    display: flex;
  }

  .input-section {
    flex: 1; /* Make both input sections take equal width */
    margin-right: 10px; /* Add some spacing between the input sections */
  }

  .total-calories{
    text-align: center;

  }
  
  
</style>