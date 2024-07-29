
<template>
  <div>
   
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Name</th>
          <th>Job Title</th>
          <th>Department</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="employee in employees" :key="employee.id">
          <td>{{ employee.id }}</td>
          <td>{{ employee.firstName }} {{ employee.lastName }}</td>
          <td>{{ employee.jobTitle }}</td>
          <td>{{ employee.department }}</td>
          <td class="action-btns"><span class="update">Edit</span> <span class="delete" @click="handleDelete(employee.id)" >Delete</span></td>
        </tr>
        
      </tbody>
    </table>
  
  </div>
</template>

<script>
const db = [
    {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "jobTitle": "Software Engineer",
      "department": "Engineering",
      "salary": 75000,
      "hireDate": "2023-11-15",
      "email": "johndoe@example.com",
      "phoneNumber": "123-456-7890"
    },
    {
      "id": 2,
      "firstName": "Jane",
      "lastName": "Smith",
      "jobTitle": "Project Manager",
      "department": "Project Management",
      "salary": 85000,
      "hireDate": "2022-05-10",
      "email": "janesmith@example.com",
      "phoneNumber": "987-654-3210"
    },
    {
      "id": 3,
      "firstName": "Michael",
      "lastName": "Johnson",
      "jobTitle": "Marketing Manager",
      "department": "Marketing",
      "salary": 90000,
      "hireDate": "2021-02-28",
      "email": "michaeljohnson@example.com",
      "phoneNumber": "555-1212"
    },
    {
      "id": 4,
      "firstName": "Emily",
      "lastName": "Brown",
      "jobTitle": "Accountant",
      "department": "Finance",
      "salary": 65000,
      "hireDate": "2024-04-18",
      "email": "emilybrown@example.com",
      "phoneNumber": "444-5555"
    },
    {
      "id": 5,
      "firstName": "David",
      "lastName": "Miller",
      "jobTitle": "Sales Representative",
      "department": "Sales",
      "salary": 70000,
      "hireDate": "2023-09-05",
      "email": "davidmiller@example.com",
      "phoneNumber": "333-7777"
    },
    {
      "id": 6,
      "firstName": "Olivia",
      "lastName": "Davis",
      "jobTitle": "HR Manager",
      "department": "Human Resources",
      "salary": 80000,
      "hireDate": "2022-12-20",
      "email": "oliviadavis@example.com",
      "phoneNumber": "222-8888"
    },
    {
      "id": 7,
      "firstName": "William",
      "lastName": "Wilson",
      "jobTitle": "IT Support",
      "department": "IT",
      "salary": 60000,
      "hireDate": "2024-01-10",
      "email": "williamwilson@example.com",
      "phoneNumber": "111-9999"
    },
    {
      "id": 8,
      "firstName": "Sophia",
      "lastName": "Jones",
      "jobTitle": "Designer",
      "department": "Design",
      "salary": 75000,
      "hireDate": "2023-07-15",
      "email": "sophiajones@example.com",
      "phoneNumber": "555-4444"
    },
    {
      "id": 9,
      "firstName": "James",
      "lastName": "Garcia",
      "jobTitle": "Developer",
      "department": "Engineering",
      "salary": 85000,
      "hireDate": "2022-03-25",
      "email": "jamesgarcia@example.com",
      
    }];  


export default {
  
    methods: {
    handleDelete(employeeId) {
      // Find the employee index based on the employeeId
      const index = this.employees.findIndex(employee => employee.id === employeeId);

      // Confirm deletion (optional)
      if (window.confirm('Are you sure you want to delete this employee?')) {
        // Remove the employee from the employees array
        this.employees.splice(index, 1);

        // Optionally, make an API call to delete the employee from the server
      }
    }
  },
  data() {
    return {
      employees: null,
    };
  },
  created() {
    this.employees = db; // Assign the imported data to the component's data
  },
};
</script>

<style scoped>
table {
  border-collapse: collapse;
  width: 100%;
}

th, td {
  border: 1px solid #ddd;
  padding: 8px;
}

th {
  text-align: left;
  background-color: #f2f2f2;
}

.action-btns{
    width:100%;
    display:flex;
    justify-content:space-around;
    align-items:center;
}
.action-btns span{
    cursor:pointer;
}
.delete{
    color:red;
}
.update{
    color:blue;
}
</style>
