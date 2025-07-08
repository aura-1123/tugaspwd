<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <title>Halaman Interaktif Sederhana</title>
  <style>
    /* Atur font dan tata letak halaman */
    body {
      font-family: Arial, sans-serif; /* Ganti jenis font di sini */
      text-align: center; /* Mengatur teks rata tengah */
      margin-top: 100px; /* Jarak atas halaman */
      transition: background-color 0.3s; /* Efek halus ganti warna latar */
    }

    /* Style tombol */
    button {
      padding: 10px 20px; /* Ukuran tombol */
      margin: 10px; /* Jarak tombol ke elemen lain */
      font-size: 16px; /* Ukuran font tombol */
      cursor: pointer; /* Cursor jadi tangan saat hover */
    }

    /* Style tempat pesan muncul */
    #pesan {
      margin-top: 20px; /* Jarak atas pesan */
      font-size: 18px; /* Ukuran teks pesan */
      color: #333; /* Warna teks pesan */
    }

    /* Style lingkaran warna yang bisa diklik */
    .warna {
      display: inline-block; /* Membuat lingkaran sejajar */
      width: 30px; /* Lebar lingkaran */
      height: 30px; /* Tinggi lingkaran */
      margin: 10px; /* Jarak antar lingkaran */
      border-radius: 50%; /* Membuat lingkaran bulat */
      cursor: pointer; /* Cursor jadi tangan saat hover */
      border: 2px solid #aaa; /* Border abu-abu lingkaran */
    }

    /* Efek saat mouse hover di lingkaran warna */
    .warna:hover {
      border-color: black; /* Border jadi hitam */
    }
  </style>
</head>
<body>

  <!-- Judul utama halaman -->
  <h2>Website Interaktif Sederhana</h2>

  <!-- Tombol yang bisa diklik -->
  <button id="tombolHalo">Klik untuk Sapa</button>

  <!-- Paragraf tempat pesan sapaan muncul -->
  <p id="pesan"></p>

  <!-- Subjudul untuk bagian ganti warna latar -->
  <h3>Ubah Warna Latar:</h3>

  <!-- Lingkaran warna, klik untuk ubah background -->
  <div class="warna" style="background-color: pink;" data-warna="pink"></div>
  <div class="warna" style="background-color: lightblue;" data-warna="lightblue"></div>
  <div class="warna" style="background-color: lightgreen;" data-warna="lightgreen"></div>

  <script>
    // Ambil tombol "Klik untuk Sapa"
    const tombol = document.getElementById("tombolHalo");

    // Ambil elemen paragraf tempat pesan muncul
    const pesan = document.getElementById("pesan");

    // Fungsi yang dijalankan saat tombol diklik
    tombol.addEventListener("click", function() {
      // Ganti isi pesan dengan teks berikut
      pesan.textContent = "Halo! Ini pesan dari AURA🎉";
    });

    // Ambil semua lingkaran warna
    const warnaPilihan = document.querySelectorAll(".warna");

    // Untuk setiap lingkaran warna, pasang event klik
    warnaPilihan.forEach(function(el) {
      el.addEventListener("click", function() {
        // Ambil nilai warna dari atribut data-warna
        const warna = el.getAttribute("data-warna");

        // Ubah warna background halaman sesuai warna terpilih
        document.body.style.backgroundColor = warna;
      });
    });
  </script>

</body>
</html>
