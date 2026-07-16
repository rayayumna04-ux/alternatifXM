<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>Alternatif Kode XM - MRF Media</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }
        
        /* Menggunakan 100dvh untuk kalkulasi tinggi layar HP yang akurat (Dynamic VH) */
        body { 
            background-color: #f4f6f9; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            height: 100vh;
            height: 100dvh; 
            width: 100vw; 
            overflow: hidden; 
            padding: 8px; 
        }
        
        .container { 
            background: #ffffff; 
            max-width: 600px; 
            width: 100%; 
            height: 100%; 
            border-radius: 14px; 
            box-shadow: 0 4px 15px rgba(0,0,0,0.05); 
            padding: 12px; 
            display: flex; 
            flex-direction: column; 
            gap: 8px; 
        }
        
        .header { text-align: center; border-bottom: 2px solid #f0f2f5; padding-bottom: 4px; flex-shrink: 0; }
        .header h1 { font-size: 16px; font-weight: 700; }

        /* Tombol dipindah ke atas agar aman dari sensor/potongan bawah layar HP */
        .action-buttons { 
            display: flex; 
            flex-direction: column; 
            flex-shrink: 0;
            z-index: 10;
        }
        
        .btn-refresh { 
            width: 100%; 
            padding: 12px; 
            border: none; 
            border-radius: 8px; 
            font-size: 13px; 
            font-weight: 700; 
            cursor: pointer;
            background-color: #0066cc; 
            color: white;
            box-shadow: 0 2px 6px rgba(0, 102, 204, 0.2);
            -webkit-tap-highlight-color: transparent;
        }
        .btn-refresh:active { background-color: #004080; }

        .notes-card { background-color: #fff8eb; border-left: 3px solid #ffb020; padding: 8px; border-radius: 6px; flex-shrink: 0; }
        .notes-card li { font-size: 10.5px; color: #4a4a4a; line-height: 1.35; margin-bottom: 3px; list-style: none; }
        .notes-card li:last-child { margin-bottom: 0; }
        .red { color: #ef4444; font-weight: 700; }

        /* Area tabel otomatis mengambil sisa space paling besar di bawah */
        .iframe-container { 
            flex-grow: 1; 
            border-radius: 8px; 
            overflow: hidden; 
            border: 1px solid #e0e0e0; 
            background: #fafafa; 
        }
        iframe { width: 100%; height: 100%; border: none; }
    </style>
</head>
<body>

<div class="container">
    <div class="header"><h1>ALTERNATIF KODE XM</h1></div>

    <!-- TOMBOL REFRESH SEKARANG DI ATAS (ANTI KEPOTONG) -->
    <div class="action-buttons">
        <button class="btn-refresh" onclick="jalankanRefresh()">
            🔄 REFRESH DATA STOK TERBARU
        </button>
    </div>

    <div class="notes-card">
        <ul>
            <li>📝 <b>Stok Real time:</b> Klik tombol di atas untuk update data sistem terbaru.</li>
            <li>🚀 <b>Sistem Detikan:</b> Mendukung transaksi detikan beda dengan KODE V.</li>
            <li>⚠️ <b>Aturan 30 Detik:</b> Order hanya 1x tiap 30 detik. <span class="red">Jika gagal & sudah unreg, tunggu 30 lalu coba lagi!</span></li>
        </ul>
    </div>

    <div class="iframe-container">
        <iframe id="stockFrame" src="https://alternatifv2mrfmedia.vercel.app/"></iframe>
    </div>
</div>

<script>
    function jalankanRefresh() {
        var iframe = document.getElementById('stockFrame');
        if (iframe) {
            iframe.src = iframe.src;
        }
    }
</script>

</body>
</html>
