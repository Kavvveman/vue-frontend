<template>
    <div class="signup">
      <h2>Sign Up</h2>
      <form @submit.prevent="handleSignup">
        <div>
          <label for="username">Username:</label>
          <input type="text"  required />
          <!-- v-model="username" -->
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email"  required />
          <!-- v-model="email" -->
        </div>
        <div>
          <label for="password">Password:</label>
          <input type="password"  required />
          <!-- v-model="password" -->
        </div>
        <button type="submit">Sign Up</button>
      </form>
    </div>
  </template>


<script>
export default {
  data() {
    return {
      username: '',
      email: '',
      password: '',
    };
  },
  methods: {
    async handleSignup() {
      // Replace with your API URL
      await fetch('https://your-backend-url/api/auth/signup', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          Username: this.Username,
          Password: this.Password,
          Email: this.Email,
          Age: this.Age
        }),
      });
    },
  },
};
</script>