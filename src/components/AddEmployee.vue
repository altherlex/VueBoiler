<template>
  <div class='container-sm'>
    <div class="alert alert-success alert-dismissible fade" v-bind:class="{ 'show':activeAlert }" role="alert">
      <strong>Well done!</strong> New employee added.
      <button type="button" class="close" data-dismiss="alert" aria-label="Close">
        <span aria-hidden="true" v-on:click="activeAlert=false">&times;</span>
      </button>
    </div>    
    <h1>Employees</h1>
    <div id='form'>
      <div class="form-group">
        <label for="employeeName">Employee Name</label>
        <input type="text" class="form-control form-control-lg" id="employeeName" v-model.lazy="name" required>
        <div class="invalid-feedback">Insert a name</div>
      </div>
      <div class="form-group">
        <label for="employeePassword">Employee Email</label>
        <input type="email" class="form-control form-control-lg" id="employeePassword" v-model.lazy="email" required>
        <div class="invalid-feedback">Insert a valid email</div>
      </div>
      <button class="btn btn-success" v-on:click="addItem">Add Employee</button>
    </div>

    <table class="table table-striped table-hover" id="employeeList">
      <thead>
        <tr>
          <th scope="col">Employee name</th>
          <th scope="col">Employee email</th>
          <th scope="col"></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in list" v-bind:key="index">
          <td>{{ item.name }}</td>
          <td>{{ item.email }}</td>
          <td><button class='btn-danger' v-on:click="deleteItem(index)">delete</button></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'AddEmployee',
  props: ['list'],
  data: function() {
    return {
      name: '',
      email: '',
      activeAlert: false
    }
  },
  methods: {
    addItem: function() {
      if ((this.name == '') || (this.email == '')){
        document.getElementById('form').classList.add('was-validated');
        this.activeAlert = false;
      }
      else {
        this.activeAlert = true;
        this.list.unshift({ name: this.name, email: this.email });
        this.name = '';
        this.email = '';
      }
    },
    deleteItem: function (index) {
      this.list.splice(index, 1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #employeeList {
    margin-top: 50px;
  }
</style>
