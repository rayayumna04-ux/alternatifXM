<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Alternatif Kode XM - MRF Media</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }
        body { background-color: #f4f6f9; display: flex; justify-content: center; align-items: center; height: 100vh; width: 100vw; overflow: hidden; padding: 10px; }
        .container { background: #ffffff; max-width: 600px; width: 100%; height: 98vh; border-radius: 16px; box-shadow: 0 5px 20px rgba(0,0,0,0.05); padding: 15px; display: flex; flex-direction: column; gap: 10px; }
        
        .header { text-align: center; border-bottom: 2px solid #f0f2f5; padding-bottom: 8px; flex-shrink: 0; }
        .header h1 { font-size: 18px; font-weight: 700; }

        /* Ringkasan Catatan 2 Baris */
        .notes-card { background-color: #fff8eb; border-left: 4px solid #ffb020; padding: 10px; border-radius: 6px; flex-shrink: 0; }
        .notes-card li { font-size: 11px; color: #4a4a4a; line-height: 1.4; margin-bottom: 4px; list-style: none; }
        .notes-card li:last-child { margin-bottom: 0; }

        .iframe-container { flex-grow: 1; border-radius: 8px; overflow: hidden; border: 1px solid #e0e0e0; background: #fafafa; }
        iframe { width: 100%; height: 100%; border: none; }

        .action-buttons { display: flex; flex-direction: column; gap: 8px; flex-shrink: 0; }
        
        /* Tombol Refresh Lebar */
        .btn-refresh { 
            width: 100%; 
            padding: 14px; 
            border: none; 
            border-radius: 8px; 
            font-size: 14px; 
            font-weight: 600; 
            cursor: pointer;
            background-color: #0066cc; 
            color: white;
            transition: background-color 0.2s ease;
        }
        .btn-refresh:hover { background-color: #0052a3; }
    </style>
</head>
<body>

<div class="container">
    <div class="header"><h1>ALTERNATIF KODE XM</h1></div>

    <div class="notes-card">
        <ul>
            <li>📝 <b>Stok Real time:</b> Silakan lakukan <b>Refresh Manual</b> untuk data terbaru.</li>
            <li>🚀 <b>Sistem Detikan:</b> Mendukung transaksi cepat tanpa kendala.</li>
            <li>⚠️ <b>Aturan 30 Detik:</b> Order hanya bisa 1x tiap 30 detik. <span class="red">Jika gagal/unreg, tunggu cooldown selesai lalu coba lagi!</span></li>
        </ul>
    </div>

    <div class="iframe-container">
        <iframe id="stockFrame" src="https://alternatifv2mrfmedia.vercel.app/"></iframe>
    </div>

    <div class="action-buttons">
        <button class="btn-refresh" onclick="document.getElementById('stockFrame').src=document.getElementById('stockFrame').src">
            🔄 Refresh Data Stok
        </button>
    </div>
</div>

</body>
</html>
