# Billy-web
web billy
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Warung Makan Interaktif</title>
    <style>
        body {
    font-family: Arial, sans-serif;
    margin: 0;
    background-color: #790c00;
    overflow-x: hidden;
}

        header {
            background-color: #790c00;
            color: white;
            padding: 20px;
            text-align: center;
        }
        nav {
            background-color: #b60000;
            padding: 10px;
            text-align: center;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
        }
        .container {
            padding: 20px;
        }
        .menu {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }
        .card {
            background: white;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        button {
            background-color: #790c00;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background-color: #219150;
        }
        footer {
            background-color: #750c00;
            color: white;
            text-align: center;
            padding: 10px;
            margin-top: 20px;
        }
        #pesanan {
            background: white;
            padding: 15px;
            border-radius: 8px;
            margin-top: 20px;
        }
        @media (max-width: 600px) {
    header h1 {
        font-size: 24px;
    }

    nav a {
        display: block;
        margin: 10px 0;
    }

    .container {
        padding: 10px;
    }

    .menu {
        grid-template-columns: 1fr;
    }

    button {
        width: 100%;
    }
}

    </style>
</head>
<body>

<header>
    <h1>Billys shop</h1>
    <p>Enak • Murah • moderen</p>
</header>

<nav>
    <a href="#menu">Menu</a>
    <a href="#pesanan">Pesanan</a>
    <a href="#kontak">Kontak</a>
</nav>

<div class="container" id="menu">
    <h2 style="color: white;">Menu Makanan</h2>
    <div class="menu">
        <div class="card">
            <h3>Chaseing hp</h3>
            <p>Rp 12.000</p>
            <button onclick="tambahPesanan('Chaseing hp', 12000)">Pesan</button>
        </div>
        <div class="card">
            <h3>Sarung tangan gaming</h3>
            <p>Rp 5.000</p>
            <button onclick="tambahPesanan('Sarung tangan gaming', 5000)">Pesan</button>
        </div>
        <div class="card">
            <h3>Coffee</h3>
            <p>Rp 18.000</p>
            <button onclick="tambahPesanan('Coffee', 18000)">Pesan</button>
        </div>
        <div class="card">
            <h3>Vocer wifi</h3>
            <p>Rp 5.000</p>
            <button onclick="tambahPesanan('Vocer wifi', 5000)">Pesan</button>
        </div>
    </div>
</div>

<div class="container" id="pesanan">
    <h2>Daftar Pesanan</h2>
    <ul id="listPesanan"></ul>
    <h3>Total: Rp <span id="total">0</span></h3>
    <button onclick="kirimPesanan()">Kirim Pesanan</button>
</div>

<div class="container" id="kontak">
    <h2>Kontak Kami</h2>
    <p>Alamat: desa sepit </p>
    <p>Telepon: 085180684964</p>
</div>

<footer>
    <p>&copy; 2025 Billys shop</p>
</footer>

<script>
    let totalHarga = 0;

    function tambahPesanan(nama, harga) {
        const list = document.getElementById('listPesanan');
        const item = document.createElement('li');
        item.textContent = nama + ' - Rp ' + harga;
        list.appendChild(item);

        totalHarga += harga;
        document.getElementById('total').textContent = totalHarga;
    }

    function kirimPesanan() {
        if (totalHarga === 0) {
            alert('Pesanan masih kosong!');
        } else {
            alert('Terima kasih! Pesanan Anda sedang diproses.');
            document.getElementById('listPesanan').innerHTML = '';
            document.getElementById('total').textContent = '0';
            totalHarga = 0;
        }
    }
</script>

</body>
</html>
