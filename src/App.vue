<template>
  <div class="dashboard">
    <div class="navbar-dashboard">
      <button @click="activeTab = 'userDetails'" :class="{ 'tab-button': activeTab === 'userDetails' }">User Details</button>
      <button @click="activeTab = 'accountCreation'" :class="{ 'tab-button': activeTab === 'accountCreation' }">Account Creation</button>
    </div>
    <component :is="activeTabComponent" class="tab-content"></component>
  </div>
</template>

<script>
import UserDetails from '@/components/UserDetails.vue';
import AccountCreation from '@/components/AccountCreation.vue';

export default {
  data() {
    return {
      activeTab: 'userDetails',
    };
  },
  computed: {
    activeTabComponent() {
      return this.activeTab === 'userDetails' ? UserDetails : AccountCreation;
    },
  },
};
</script>

<style>
/* Add your component-specific styles here */
/* Add your Tailwind CSS styles for the dashboard here */

/* Add your navbar styles here */


.dashboard {
  display: flex;
  flex-direction: column;
  height: 100vh;
  width:100%;
}

button {
  color: #110101;
  text-decoration: none;
  padding: 15px 20px;
  border-radius: 6px;
  transition: background-color 0.3s ease, opacity 1s ease; /* Added opacity transition */
  opacity: 1; 
}
.navbar-dashboard {
  background-color: #3490dc;
  padding: 1rem;
  display: flex;
  justify-content: left;
  align-items: center;
}

.tab-button {
  background-color: #3490dc;
  color: #fff;
  padding: 10px 15px;
  border: none;
  cursor: pointer;
  text-decoration: none;
  transition: background-color 0.3s ease;
}

.tab-button:hover {
  background-color: #2779bd;
}

/* 
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
}

.dashboard {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.tab-button {
  background-color: #3490dc;
  color: #fff;
  padding: 10px 15px;
  border: none;
  cursor: pointer;
}

.tab-button:hover {
  background-color: #2779bd;
}

.tab-content {
  flex-grow: 1;
  padding: 20px;
  width: 100%; 
  box-sizing: border-box; 

}

html, body {
  width: 100%;
  overflow-x: hidden;
} */

  
</style>


