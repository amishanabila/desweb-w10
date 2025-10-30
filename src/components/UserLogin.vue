<template>
  <div class="login">
    <h1>Login</h1> 
    <form @submit.prevent="handleLogin">
      <div>
        <label for="username" class="label">Username:</label>
        <input type="text" v-model="username" required class="input-field" />
      </div>
      <div>
        <label for="password" class="label">Password:</label>
        <input type="password" v-model="password" required class="input-field" />
      </div>
      <button type="submit" class="login-button">Login</button>
      <p v-if="errorMessage" class="error">{{ errorMessage }}</p>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      errorMessage: '' 
    };
  },
  methods: {
    handleLogin() {
      if (this.username === 'admin' && this.password === 'admin') {
        this.$emit('loginSuccess');
        this.errorMessage = '';
      } else {
        this.errorMessage = 'Invalid username or password';
      }
    }
  }
};
</script>

<style>
.error {
  color: red;
}

.label {
  font-size: 20px; 
}

.input-field {
  height: 25px; 
  width: 250px; 
  font-size: 16px; 
  border-radius: 3px;
}

.login-button {
  font-size: 18px; 
  padding: 5px 8px; 
  border-radius: 3px;
}
</style>
