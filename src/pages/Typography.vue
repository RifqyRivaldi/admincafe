<template>
  <div class="container">
    <h2>Input Data</h2>
    <div class="form-group">
      <label for="name">Name:</label>
      <input type="text" v-model="name" placeholder="Enter your name">
    </div>
    <div class="form-group">
      <label for="email">Email:</label>
      <input type="email" v-model="email" placeholder="Enter your email">
    </div>
    <div class="form-group">
      <label for="password">Password:</label>
      <input type="password" v-model="Password" placeholder="Enter your Password">
    </div>
    <button @click="submitForm">Submit</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      password
    };
  },
  methods: {
    submitForm() {
      // Di sini Anda bisa menambahkan logika untuk mengirim data atau melakukan validasi
      console.log('Name:', this.name);
      console.log('Email:', this.email);
      console.log('Password:', this.password);
      // Contoh validasi sederhana
      if (!this.name || !this.email) {
        alert('Name, Email And Password dimasukkan tolol');
      } else {
        alert('Name, Email And Password sudah bisa cok!!!');
        // Di sini Anda bisa mengirim data ke server atau melakukan hal lainnya
      }
    }
  }
};
</script>

<style scoped>
.container {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
  max-width: 400px;
  width: 100%;
}

.form-group {
  margin-bottom: 20px;
}

label {
  font-weight: bold;
  display: block;
  margin-bottom: 5px;
}

input[type="text"],
input[type="email"] {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
</style>
