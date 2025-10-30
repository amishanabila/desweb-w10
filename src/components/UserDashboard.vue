<template>
  <div class="dashboard">
    <h1>Welcome to the Dashboard</h1>
    <p>You are logged in.</p>
    <button @click="logout">Logout</button> 
  </div>
</template>

<script>
export default {
  name: 'UserDashboard',
  methods: {
    logout() {
      this.$emit('logout');
    }
  }
};
</script>

<style scoped>
.dashboard {
  text-align: center;
}

p {
  font-size: 22px;
}

button {
  font-size: 18px; 
  padding: 3px 9px; 
  border-radius: 3px;
}
</style>