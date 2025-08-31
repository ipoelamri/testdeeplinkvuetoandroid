<template>
  <div>
    <h2>Tekan tombol di bawah untuk membuka aplikasi</h2>
    <button @click="openApp" class="btn">Buka Aplikasi Saya</button>
  </div>
</template>

<script>
export default {
  name: "OpenAppButton", // Nama komponen Vue
  methods: {
    openApp() {
      // 1. Definisikan URL scheme untuk aplikasi Anda.
      // Ganti 'myappb://' dengan URL scheme yang sesuai dengan konfigurasi AndroidManifest.xml Anda.
      const appUrl = "myappb://";

      // 2. Definisikan URL Play Store untuk fallback.
      // Ganti 'com.contoh.aplikasi' dengan package name aplikasi Anda di Play Store.
      const playStoreUrl =
        "https://play.google.com/store/apps/details?id=com.contoh.aplikasi";

      // 3. Coba buka aplikasi dengan URL scheme.
      window.location.href = appUrl;

      // 4. Tambahkan fallback.
      // Gunakan setTimeout agar ada jeda waktu (misalnya 500ms) untuk
      // memberikan kesempatan pada perangkat untuk membuka aplikasi.
      // Jika aplikasi tidak terbuka, browser akan melanjutkan ke Play Store.
      setTimeout(() => {
        window.location.href = playStoreUrl;
      }, 500);
    },
  },
};
</script>

<style scoped>
/* Contoh styling sederhana untuk tombol */
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
