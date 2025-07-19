<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Lirik Nanti Kita Seperti Ini - Batas Senja</title>
  <style>
    body {
      background: #222;
      color: #fff;
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }
    .lirik {
      font-size: 2rem;
      margin: 20px;
      text-align: center;
      min-height: 60px;
      transition: opacity 0.5s;
      opacity: 1;
    }
    .judul {
      font-size: 1.2rem;
      margin-bottom: 30px;
      color: #ffe066;
      letter-spacing: 1px;
    }
  </style>
</head>
<body>
  <div class="judul">Lirik Lagu "Nanti Kita Seperti Ini" - Batas Senja</div>
  <div class="lirik" id="lirik"></div>
  <script>
    const lirik = [
      // Verse 1
      "Ini gambaran kita suatu hari nanti",
      "Setelah sekian lama kita jalani",
      "Lewati masa‑masa yang berarti",
      "Kini, ku sudah yakin pada satu hati",
      "Yang kurasa tepat untuk temani",
      "Sekarang hingga aku tua nanti",
      // Pre-ref
      "Ingin punya rumah",
      "Tuk tempat bermesra",
      "Kau dipanggil ibu, sementara aku ayah",
      "Bertukar cerita",
      "Di ruang keluarga",
      "Bercengkrama dan menimang buah hati kita",
      // Chorus
      "Sederhana",
      "Bahagia ini lengkap sudah",
      "Sama‑sama",
      "Hingga nanti kita tutup mata",
      // Bridge (Ha-aah 3x)
      "Ha‑aah",
      "Ha‑aah",
      "Ha‑aah",
      // Verse 2
      "Ingin punya rumah",
      "Tuk tempat bermesra",
      "Kau dipanggil ibu, sementara aku ayah",
      "Bertukar cerita hingga lelap mata",
      "Lalu datang pagi, kau memasak, ku bekerja",
      // Chorus 2
      "Sederhana",
      "Bahagia ini lengkap sudah",
      "Sama‑sama",
      "Hingga nanti ajal kita tiba",
      // Outro
      "Semoga saja",
      "Niat baik kan terwujud segera",
      "Asal kita",
      "Percaya Dia Maha Segalanya",
      "Jangan dulu lelah, yakin semua indah",
      "Pejamkanlah mata, pada‑Nya kita berserah"
    ];

    // Jeda per baris (ms), sesuai nada lagu
    const jeda = [
      // Verse 1
      4500, 4500, 4500, 4500, 4500, 4500,
      // Pre-ref
      3500, 3500, 6000, 3500, 3500, 6000,
      // Chorus
      3000, 4000, 3000, 5000,
      // Bridge (Ha-aah 3x)
      2500, 2500, 2500,
      // Verse 2
      3500, 3500, 6000, 6000, 6000,
      // Chorus 2
      3000, 4000, 3000, 5000,
      // Outro
      3000, 4000, 3000, 4000, 5000, 6000
    ];

    let idx = 0;
    const lirikDiv = document.getElementById('lirik');

    function tampilkanLirik() {
      if (idx >= lirik.length) return;
      lirikDiv.style.opacity = 0;
      setTimeout(() => {
        lirikDiv.textContent = lirik[idx] || "";
        lirikDiv.style.opacity = 1;
        idx++;
        if (idx < lirik.length) {
          setTimeout(tampilkanLirik, jeda[idx-1] || 3000);
        }
      }, 500);
    }

    tampilkanLirik();
  </script>
</body>
</html> 
