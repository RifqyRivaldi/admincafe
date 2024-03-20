<template>
  <div class="cafe-list">
    <h2 class="section-title">Daftar Kafe</h2>
    <table class="table-container">
      <thead>
        <tr>
          <th>No</th>
          <th>Nama Kafe</th>
          <th>Alamat</th>
          <th>Kota</th>
          <th>Rating</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(cafe, index) in cafes" :key="cafe.id">
          <td>{{ index + 1 }}</td>
          <td>{{ cafe.name }}</td>
          <td>{{ cafe.address }}</td>
          <td>{{ cafe.city }}</td>
          <td>{{ cafe.rating }}</td>
          <td>
            <router-link :to="'/edit-data/' + cafe.id" class="button-link">Edit</router-link>
            <button @click="deleteCafe(cafe.id)" class="button-delete">Delete</button>
          </td>
        </tr>
      </tbody>
    </table>
    <!-- Tambahkan tombol untuk menuju ke halaman "create" -->
    <div class="button-container">
      <router-link to="/create" class="custom-button">Tambah Kafe</router-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cafes: [
        { id: 1, name: "Kafe A", address: "Jl. Pahlawan No. 123", city: "Jakarta", rating: 4.5 },
        { id: 2, name: "Kafe B", address: "Jl. Merdeka No. 456", city: "Bandung", rating: 4.2 },
        { id: 3, name: "Kafe C", address: "Jl. Patriot No. 789", city: "Surabaya", rating: 4.8 },
        { id: 4, name: "Kafe D", address: "Jl. Mandiri No. 101", city: "Yogyakarta", rating: 4.3 },
        { id: 5, name: "Kafe E", address: "Jl. Berkah No. 202", city: "Semarang", rating: 4.7 }
      ]
    };
  },
  methods: {
    deleteCafe(id) {
      // Fungsi untuk menghapus kafe dengan ID tertentu
      console.log("Menghapus kafe dengan ID:", id);
      // Tulis logika untuk menghapus kafe dari daftar atau panggil API untuk menghapusnya dari server
    }
  }
};
</script>

<style scoped>
/* Gaya CSS untuk tabel */
.cafe-list {
  font-family: Arial, sans-serif;
  margin: 20px;
}

.section-title {
  font-size: 1.5rem;
  margin-bottom: 20px;
}

.table-container {
  width: 100%;
  border-collapse: collapse;
}

th, td {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

th {
  background-color: #f2f2f2;
}

tr:hover {
  background-color: #f5f5f5;
}

/* Gaya CSS untuk tombol */
.custom-button, .button-link, .button-delete {
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  margin-right: 10px;
}

.custom-button:hover, .button-link:hover, .button-delete:hover {
  background-color: #0056b3;
}

.button-container {
  margin-top: 20px;
}
</style>
