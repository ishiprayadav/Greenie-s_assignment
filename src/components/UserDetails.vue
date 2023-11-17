<template>
    <div class="table-container">
      <h2 class="UserDetailsHeader">User Details</h2>
      <input v-model="searchTerm" placeholder="Search users" class="search-input" />
      <table class="user-table">
        <thead>
          <tr>
            <th>Username</th>
            <th>Email</th>
            <th>Phone</th>
            <th>ID</th>
            <th>Creation Date</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="user in filteredUsers" :key="user.id">
            <td>{{ user.username }}</td>
            <td>{{ user.email }}</td>
            <td>{{ user.phone }}</td>
            <td>{{ user.id }}</td>
            <td>{{ user.creationDate }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        searchTerm: '',
        users: [
          { id: 1, username: 'user1', email: 'user1@example.com', phone: '123-456-7890', creationDate: '2023-01-01' },
          // Add more user data as needed
        ],
      };
    },
    computed: {
      filteredUsers() {
        return this.users.filter(user =>
          user.username.toLowerCase().includes(this.searchTerm.toLowerCase())
        );
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add your component-specific styles here */
  /* Add your custom styles for UserDetails.vue here */


.table-container {
  max-width: 800px;
  margin: 0 auto;
}

.search-input {
  width: 100%;
  padding: 0.75rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  margin-bottom: 1rem;
}

.user-table {
  width: 100%;
  border-collapse: collapse;
}

.user-table th,
.user-table td {
  border: 1px solid #ccc;
  padding: 0.75rem;
  text-align: left;
}

.user-table th {
  background-color: #3490dc;
  color: #fff;
}

.user-table tbody tr:hover {
  background-color: #f5f5f5;
}

  </style>
  