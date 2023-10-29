<template>
  <div class="calendar">
    <div class="day" v-for="day in days" :key="day" @mouseover="highlightDay(day)" @click="selectDay(day)" :class="{ hover: hoverDay === day, selected: selectedDays.includes(day) }">
      {{ day }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedDays: [],
      hoverDay: null,
    };
  },
  computed: {
    days() {
      const daysInMonth = new Date(this.year, this.month + 1, 0).getDate();
      return Array.from({ length: daysInMonth }, (_, i) => i + 1);
    },
  },
  props: {
    year: Number,
    month: Number,
  },
  methods: {
    highlightDay(day) {
      this.hoverDay = day;
    },
    selectDay(day) {
      if (this.selectedDays.includes(day)) {
        this.selectedDays = this.selectedDays.filter((d) => d !== day);
      } else {
        this.selectedDays.push(day);
      }
    },
  },
};
</script>

<style scoped>
.calendar {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 5px;
  width: 300px;
  margin: 0 auto;
  font-family: Arial, sans-serif;
}

.day {
  width: 40px;
  height: 40px;
  text-align: center;
  line-height: 40px;
  cursor: pointer;
  border: 1px solid #ccc;
}

.day.hover {
  background-color: #eee;
}

.day.selected {
  background-color: #007bff;
  color: #fff;
}
</style>
