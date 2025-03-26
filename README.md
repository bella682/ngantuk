# ngantuk
dark sistem lu gw baca yang kai
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Registrasi Anggota Perpustakaan</title>
    <link rel="stylesheet" href="style.css">
    <script>
        function simpanData(event) {
            event.preventDefault(); // Mencegah halaman refresh

            let nama = document.getElementById("nama").value;
            let email = document.getElementById("email").value;
            let telepon = document.getElementById("telepon").value;
            let alamat = document.getElementById("alamat").value;
            let gender = document.querySelector('input[name="gender"]:checked').value;
            let tanggalLahir = document.getElementById("tanggalLahir").value;
            let password = document.getElementById("password").value;
            let ulangiPassword = document.getElementById("ulangiPassword").value;

            if (password !== ulangiPassword) {
                alert("Password tidak cocok!");
                return;
            }

            let anggota = JSON.parse(localStorage.getItem("anggota")) || [];
            anggota.push({ nama, email, telepon, alamat, gender, tanggalLahir });

            localStorage.setItem("anggota", JSON.stringify(anggota));

            window.location.href = "anggota.html"; // Arahkan ke halaman anggota.html
        }
    </script>
</head>
<body>
    <h2>Registrasi Anggota Perpustakaan</h2>
    <form onsubmit="simpanData(event)">
        <label for="nama">Nama Lengkap:</label>
        <input type="text" id="nama" name="nama" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="telepon">Nomor Telepon:</label>
        <input type="number" id="telepon" name="telepon" required>

        <label for="alamat">Alamat:</label>
        <textarea id="alamat" name="alamat" required></textarea>

        <label>Jenis Kelamin:</label>
        <div class="gender-container">
            <input type="radio" id="laki" name="gender" value="Laki-laki" required>
            <label for="laki">Laki-laki</label>

            <input type="radio" id="perempuan" name="gender" value="Perempuan">
            <label for="perempuan">Perempuan</label>
        </div>

        <label for="tanggalLahir">Tanggal Lahir:</label>
        <input type="date" id="tanggalLahir" name="tanggalLahir" required>

        <label for="password">Buat Password:</label>
        <input type="password" id="password" name="password" required>

        <label for="ulangiPassword">Ulangi Password:</label>
        <input type="password" id="ulangiPassword" name="ulangiPassword" required>

        <button type="submit">Daftar</button>
    </form>
</body>
body {
    font-family: Arial, sans-serif;
    background-color: #f9f9f9;
    margin: 0;
    padding: 20px;
}

h2 {
    text-align: center;
}

form {
    background-color: #f2f2f2;
    padding: 20px;
    width: 300px;
    margin: 0 auto;
    border-radius: 5px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

label {
    display: block;
    margin-top: 10px;
    font-weight: bold;
}

input, textarea {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

.gender-container {
    display: flex;
    gap: 10px;
    align-items: center;
    margin-top: 5px;
}

button {
    width: 100%;
    padding: 10px;
    margin-top: 15px;
    background-color: blue;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: darkblue;
}

table {
    width: 80%;
    margin: 20px auto;
    border-collapse: collapse;
    background-color: white;
}

th, td {
    border: 1px solid black;
    padding: 8px;
    text-align: left;
}

th {
    background-color: #ddd;
}

tr:nth-child(even) {
    background-color: #f2f2f2;
}
</html>
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daftar Anggota Perpustakaan</title>
    <link rel="stylesheet" href="style.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }
        table {
            width: 50%;
            border-collapse: collapse;
            background: white;
            border-radius: 6px;
            overflow: hidden;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: #007BFF;
            color: white;
        }
        tr:nth-child(even) {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>
    <h2>Daftar Anggota Perpustakaan</h2>
    <table>
        <tr>
            <th>No</th>
            <th>Nama Lengkap</th>
            <th>Email</th>
            <th>Nomor Telepon</th>
            <th>Jenis Kelamin</th>
        </tr>
        <tr>
            <td>1</td>
            <td>Andi Wijaya</td>
            <td>andi@mail.com</td>
            <td>08123456789</td>
            <td>Laki-laki</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Siti Rahma</td>
            <td>siti@mail.com</td>
            <td>08987654321</td>
            <td>Perempuan</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Budi Santoso</td>
            <td>budi@mail.com</td>
            <td>08223344556</td>
            <td>Laki-laki</td>
        </tr>
    </table>
</body>
</html>


