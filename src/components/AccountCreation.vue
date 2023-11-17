

<template>
    <div class="container">
      <h2 class="text-2xl font-bold mb-4">Account Creation</h2>
      <form @submit.prevent="createAccount" class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
        <div class="mb-4">
          <label for="username" class="block text-gray-700 text-sm font-bold mb-2">Username:</label>
          <input v-model="newUser.username" type="text" id="username" class="input-field" />
        </div>
        <div class="mb-6">
          <label for="password" class="block text-gray-700 text-sm font-bold mb-2">Password:</label>
          <input v-model="newUser.password" type="password" id="password" class="input-field" />
        </div>
        <button type="submit" class="button-primary">Create Account</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newUser: {
          username: '',
          password: '',
        },
      };
    },
    methods: {
      createAccount() {
        // Dummy request handling (replace this with your actual API call)
        console.log('Creating account with the following data:', this.newUser);
  
        // Reset the form after submission
        this.newUser = {
          username: '',
          password: '',
        };
      },
    },
  };
  </script>
  
  <style scoped>
  
  /* Add your component-specific styles here */
 /* Add your specific styles for AccountCreation.vue here */
body {
  background-color: #f3f4f6;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  margin: 0;
  font-family: 'Lucida Sans';
}

.container {
  max-width: 400px;
  align-items: center;
  align-self: center;
}

.input-field {
  width: 100%;
  padding: 8px;
  margin-bottom: 1rem;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.button-primary {
  background-color: #3490dc;
  color: #fff;
  padding: 10px 15px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.button-primary:hover {
  background-color: #2779bd;
}

  </style>
  
  
  