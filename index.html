<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aplikasi Kwitansi</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script>
        function terbilangToRupiah(terbilang) {
            const numberWords = {
                'nol': 0, 'satu': 1, 'dua': 2, 'tiga': 3, 'empat': 4,
                'lima': 5, 'enam': 6, 'tujuh': 7, 'delapan': 8, 'sembilan': 9,
                'puluh': 10, 'ratus': 100, 'seratus': 100, 'ribu': 1000, 'juta': 1000000
            };

            const words = terbilang.split(" ");
            let total = 0;
            let current = 0;

            words.forEach(word => {
                if (numberWords[word] !== undefined) {
                    if (word === 'puluh' || word === 'ratus' || word === 'ribu' || word === 'juta') {
                        current *= numberWords[word];
                    } else {
                        current += numberWords[word];
                    }
                } else {
                    total += current;
                    current = 0; // reset current for the next segment
                }
            });

            total += current; // add any remaining value
            return new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR' }).format(total);
        }

        function updateNominal() {
            const terbilang = document.getElementById("terbilang").value;
            const nominal = terbilangToRupiah(terbilang);
            document.getElementById("nominal").value = nominal;
            document.getElementById("displayNominal").innerText = nominal;
        }

        async function cetakPDF() {
            const { jsPDF } = window.jspdf;

            const doc = new jsPDF();
            const tanggal = document.getElementById("tanggal").value;
            const terimaDari = document.getElementById("terimaDari").value;
            const terbilang = document.getElementById("terbilang").value;
            const untukPembayaran = document.getElementById("untukPembayaran").value;
            const nominal = document.getElementById("nominal").value;

            doc.text("Kwitansi", 105, 20, { align: "center" });
            doc.text(`Tanggal Pembayaran: ${tanggal}`, 10, 40);
            doc.text(`Terima Dari: ${terimaDari}`, 10, 50);
            doc.text(`Terbilang: ${terbilang}`, 10, 60);
            doc.text(`Untuk Pembayaran: ${untukPembayaran}`, 10, 70);
            doc.text(`Nominal Rupiah: ${nominal}`, 10, 80);
            doc.text("Terima kasih atas pembayaran Anda!", 105, 90, { align: "center" });

            // Menambahkan gambar stempel jika ada
            const imgData = await fetch("stempel.png").then(res => res.blob()).then(blob => {
                return new Promise((resolve) => {
                    const reader = new FileReader();
                    reader.onloadend = () => resolve(reader.result);
                    reader.readAsDataURL(blob);
                });
            });

            doc.addImage(imgData, "PNG", 80, 95, 50, 50); // Menambahkan gambar stempel
            doc.save("kwitansi.pdf");
        }
    </script>
</head>
<body class="bg-gray-100 p-10">
    <div class="container mx-auto bg-white p-8 shadow-md rounded-lg">
        <h2 class="text-2xl font-bold mb-6">Form Kwitansi</h2>
        <form>
            <div class="mb-4">
                <label for="tanggal" class="block text-sm font-medium text-gray-700">Tanggal Pembayaran</label>
                <input type="date" id="tanggal" class="mt-1 p-2 border border-gray-300 rounded-md w-full">
            </div>
            <div class="mb-4">
                <label for="terimaDari" class="block text-sm font-medium text-gray-700">Terima Dari</label>
                <input type="text" id="terimaDari" class="mt-1 p-2 border border-gray-300 rounded-md w-full">
            </div>
            <div class="mb-4">
                <label for="terbilang" class="block text-sm font-medium text-gray-700">Terbilang</label>
                <input type="text" id="terbilang" class="mt-1 p-2 border border-gray-300 rounded-md w-full" oninput="updateNominal()">
            </div>
            <div class="mb-4">
                <label for="untukPembayaran" class="block text-sm font-medium text-gray-700">Untuk Pembayaran</label>
                <input type="text" id="untukPembayaran" class="mt-1 p-2 border border-gray-300 rounded-md w-full">
            </div>
            <div class="mb-4">
                <label for="nominal" class="block text-sm font-medium text-gray-700">Nominal Rupiah</label>
                <input type="text" id="nominal" class="mt-1 p-2 border border-gray-300 rounded-md w-full" readonly>
            </div>
            <button type="button" onclick="cetakPDF()" class="mt-4 bg-blue-500 text-white px-4 py-2 rounded-md">Cetak PDF</button>
        </form>
    </div>

    <div id="receipt" class="hidden">
        <div class="container mx-auto bg-white p-8 shadow-md rounded-lg">
            <h2 class="text-3xl font-bold text-center mb-6">Kwitansi</h2>
            <div class="flex justify-between items-center mb-4">
                <p><strong>Tanggal Pembayaran:</strong> <span id="displayTanggal"></span></p>
            </div>
            <p><strong>Terima Dari:</strong> <span id="displayTerimaDari"></span></p>
            <p><strong>Terbilang:</strong> <span id="displayTerbilang"></span></p>
            <p><strong>Untuk Pembayaran:</strong> <span id="displayUntukPembayaran"></span></p>
            <p class="text-xl font-bold mt-4"><strong>Nominal Rupiah:</strong> <span id="displayNominal"></span></p>
            <p class="mt-6 text-center">Terima kasih atas pembayaran Anda!</p>
            <div class="flex justify-center mt-4">
                <img src="stempel.png" alt="Stempel" class="w-24 h-auto">
            </div>
        </div>
    </div>

    <script>
        const inputs = document.querySelectorAll("input");
        inputs.forEach(input => {
            input.addEventListener("input", () => {
                document.getElementById(`display${input.id.charAt(0).toUpperCase() + input.id.slice(1)}`).innerText = input.value;
            });
        });
    </script>
</body>
</html>
