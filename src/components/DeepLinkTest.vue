<template>
  <div class="text-center">
    <h2>Tekan tombol di bawah untuk membuka aplikasi</h2>
    <button @click="openApp" class="btn">Buka Aplikasi Saya</button>
  </div>
</template>

<script>
export default {
  name: "OpenAppButton", // Nama komponen Vue
  methods: {
    openApp() {
      // const appUrl = "mydlapp://";
      const appUrl = "mecollectproline://";
      const playStoreUrl =
        "https://play.google.com/store/apps/details?id=com.contoh.aplikasi";
      window.location.href = appUrl;

      setTimeout(() => {
        window.location.href = playStoreUrl;
      }, 500);
    },
  },
};
</script>

<style scoped>
.btn {
  background-color: #42b983; /* Warna hijau khas Vue.js */
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s ease;
}

.btn:hover {
  background-color: #357a62;
}

h2 {
  color: #333;
  margin-bottom: 20px;
}
</style>
