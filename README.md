<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alternatif Kode XM - MRF Media</title>
    <!-- Google Fonts untuk tampilan modern -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
        }

        body {
            background-color: #f4f6f9;
            color: #333;
            line-height: 1.6;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            background: #ffffff;
            max-width: 500px;
            width: 100%;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            padding: 30px;
        }

        .header {
            text-align: center;
            margin-bottom: 25px;
            border-bottom: 2px solid #f0f2f5;
            padding-bottom: 15px;
        }

        .header h1 {
            font-size: 24px;
            color: #1a1a1a;
            font-weight: 700;
        }

        .header p {
            font-size: 14px;
            color: #666;
            margin-top: 5px;
        }

        /* Bagian Catatan/Notes */
        .notes-card {
            background-color: #fff8eb;
            border-left: 4px solid #ffb020;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 25px;
        }

        .notes-card h3 {
            font-size: 14px;
            color: #b76e00;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .notes-card ul {
            list-style: none;
        }

        .notes-card li {
            font-size: 13px;
            color: #4a4a4a;
            margin-bottom: 6px;
            display: flex;
            align-items: flex-start;
            gap: 8px;
        }

        /* Embed Iframe dari Link Utama */
        .iframe-container {
            position: relative;
            width: 100%;
            height: 350px;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid #e0e0e0;
            margin-bottom: 20px;
            background: #fafafa;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Tombol Aksi */
        .action-buttons {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .btn {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 8px;
            font-size: 15px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 8px;
            text-decoration: none;
        }

        .btn-refresh {
            background-color: #0066cc;
            color: white;
        }

        .btn-refresh:hover {
            background-color: #0052a3;
        }

        .btn-order {
            background-color: #22c55e;
            color: white;
        }

        .btn-order:hover {
            background-color: #16a34a;
        }

        .btn:disabled {
            background-color: #cbd5e1;
            color: #64748b;
            cursor: not-allowed;
        }

        .cooldown-text {
            text-align: center;
            font-size: 12px;
            color: #ef4444;
            font-weight: 500;
            margin-top: 5px;
            display: none;
        }

        .footer {
            text-align: center;
            margin-top: 25px;
            font-size: 11px;
            color: #999;
        }
    </style>
</head>
<body>

<div class="container">
    <div class="header">
        <h1>ALTERNATIF KODE XM</h1>
        <p>MRF Media Stock Monitor</p>
    </div>

    <!-- Papan Pengumuman / Aturan Sistem -->
    <div class="notes-card">
        <h3>⚠️ INFORMASI PENTING:</h3>
        <ul>
            <li>📝 Stok di-update otomatis sesuai sistem.</li>
            <li>📝 Lakukan Refresh Manual untuk update sisa stok terupdate.</li>
            <li>📝 Orderan detikan.</li>
            <li>📝 Stok hanya bisa diorder 1 kali setiap 30 detik. Jika order (sudah unreg) masih gagal, kemungkinan reseller lain baru saja transaksi. Tunggu timer selesai lalu coba kembali.</li>
        </ul>
    </div>

    <!-- Menampilkan Halaman Vercel Asli di Dalam Web -->
    <div class="iframe-container">
        <iframe id="stockFrame" src="https://alternatifv2mrfmedia.vercel.app/" title="Stok XM"></iframe>
    </div>

    <!-- Tombol Kontrol -->
    <div class="action-buttons">
        <button class="btn btn-refresh" onclick="refreshStok()">
            🔄 Refresh Data Stok
        </button>
        
        <button class="btn btn-order" id="orderBtn" onclick="startOrderCooldown()">
            🚀 Ambil / Order Stok (Detikan)
        </button>
        <div class="cooldown-text" id="cooldownText">Harap tunggu <span id="timer">30</span> detik sebelum melakukan order ulang!</div>
    </div>

    <div class="footer">
        &copy; 2026 MRF Media. All Rights Reserved.
    </div>
</div>

<script>
    // Fungsi untuk me-refresh iframe stok secara manual
    function refreshStok() {
        const iframe = document.getElementById('stockFrame');
        iframe.src = iframe.src; // Memaksa iframe reload data terbaru
    }

    // Fungsi untuk handle jeda (cooldown) 30 detik saat klik order
    function startOrderCooldown() {
        const orderBtn = document.getElementById('orderBtn');
        const cooldownText = document.getElementById('cooldownText');
        const timerSpan = document.getElementById('timer');
        
        let timeLeft = 30;
        
        // Disable tombol order
        orderBtn.disabled = true;
        cooldownText.style.display = 'block';
        
        // Buka link orderan asli di tab baru (sesuaikan jika ada link trx eksternal)
        window.open('https://alternatifv2mrfmedia.vercel.app/', '_blank'); 

        const countdown = setInterval(() => {
            timeLeft--;
            timerSpan.textContent = timeLeft;
            
            if (timeLeft <= 0) {
                clearInterval(countdown);
                orderBtn.disabled = false;
                cooldownText.style.display = 'none';
                timerSpan.textContent = "30";
            }
        }, 1000);
    }
</script>

</body>
</html>
