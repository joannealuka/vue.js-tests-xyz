<template>
  <div class="employee">
    <div class="avatar">
      <img :src="avatar" :alt="name" />
    </div>
    <div class="details">
      <h1>
        Name:
        <span>{{name}}</span>
      </h1>
      <h3>
        Department:
        <span>{{department}}</span>
      </h3>
      <h5>
        Salary:
        <span>{{salary}}</span>
      </h5>
      <p>
        Gender:
        <span>{{gender}}</span>
      </p>
      <p>
        Age:
        <span>{{age}}</span>
      </p>
    </div>
    <div class="controlls">
      <a :href="`tel:${employee.phone}`">Call</a>
      <a :href="`mailto:${employee.email}`">Email</a>
    </div>
  </div>
</template>

<script>
import Employees from "@/data/employees.json";

export default {
  name: "Employee",
  data() {
    return {
      employees: Employees,
      employee: []
    };
  },
  methods: {
    getEmployeeData() {
      var i, employees;
      employees = this.employees;

      for (i = 0; i < employees.length; i++) {
        if (employees[i].slug == this.$route.params.slug) {
          this.employee = employees[i];
          break;
        }
      }
    }
  },
  computed: {
    avatar() {
      return require(`@/assets/employees/${this.employee.avatar}`);
    },
    name() {
      return this.employee.name;
    },
    department() {
      return this.employee.department;
    },
    salary() {
      return this.employee.salary;
    },
    gender() {
      return this.employee.gender;
    },
    age() {
      return this.employee.age;
    }
  },
  created() {
    this.getEmployeeData();
  }
};
</script>

<style lang="scss" scoped>
.employee {
  margin: -20px 40px;
  padding: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-flow: row wrap;
  background: #fff;

  .avatar,
  .details {
    flex: 0 0 50%;
  }

  .avatar {
    height: 400px;
    width: 300px;
    border-radius: 10px;
    overflow: hidden;
  }

  .details {
    padding: 20px;
    line-height: 3em;
    align-self: flex-start;
  }

  .controlls {
    margin: 20px 0;
    padding: 15px;
    width: 100%;
    flex: 0 0 100%;
    display: flex;
    align-items: center;
    justify-content: flex-end;

    a {
      display: block;
      margin: 0 20px;
      padding: 10px 20px;
      text-decoration: none;
      background: teal;
      color: white;
      border-radius: 10px;
      outline: none;
    }
  }
}
</style>
