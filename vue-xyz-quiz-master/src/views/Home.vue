<template>
  <div class="home">
    <div class="grid-wrapper">
      <div v-for="employee in employees" :key="employee.id">
        <thumbnail
          :name="employee.name"
          :department="employee.department"
          :avatar="employee.avatar"
          :slug="employee.slug"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Thumbnail from "@/components/Thumbnail.vue";
import Employees from "@/data/employees.json";

export default {
  name: "Home",
  components: {
    Thumbnail
  },
  data() {
    return {
      employees: Employees
    };
  }
};
</script>

<style lang="scss" scoped>
.grid-wrapper {
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  align-items: center;
  justify-content: space-evenly;
}
</style>