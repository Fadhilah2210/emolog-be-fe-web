# 📔 Emolog - Emotion Journal App

**Emolog** adalah aplikasi journaling harian berbasis web yang dilengkapi fitur analisis sentimen menggunakan AI. Aplikasi ini membantu pengguna merefleksikan perasaan mereka setiap hari melalui catatan dan emosi yang terekam secara otomatis.

---

## 🛠️ Teknologi yang Digunakan

- **Frontend:** JavaScript (Vite)
- **Backend:** Laravel 10+
- **Analisis Sentimen:** Python (BERT-based model dengan Flask)
- **Database:** MySQL (XAMPP)
- **Local Server:** XAMPP (Apache + MySQL)

---

## 🚀 Cara Menjalankan Project Secara Lokal

### 1. Jalankan XAMPP
- Aktifkan **Apache** dan **MySQL** melalui XAMPP Control Panel.

### 2. Kloning dan Install Dependency
```bash
git clone <repository-url>
cd emolog
composer install
npm install
```

### 3. Konfigurasi Environment
- Duplikat file `.env.example` dan ubah nama menjadi `.env`
- Atur konfigurasi database di dalam `.env`, contohnya:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=emolog
DB_USERNAME=root
DB_PASSWORD=
```

- Generate application key:
```bash
php artisan key:generate
```

- Jalankan migrasi jika diperlukan:
```bash
php artisan migrate
```

### 4. Jalankan Analisis Sentimen (Python)
- Pastikan kamu sudah menginstall Python dan `pip`.
- Masuk ke direktori tempat file Python `sentiment_api.py` berada:
```bash
cd sentiment-analysis
python sentiment_api.py
```

> Pastikan dependensi seperti `transformers`, `torch`, dan `flask` sudah terpasang.

Contoh install dependensi:
```bash
pip install -r requirements.txt
```
_atau jika tidak ada file `requirements.txt` bisa manual:_
```bash
pip install flask torch transformers
```

### 5. Jalankan Frontend
```bash
npm run dev
```

### 6. Jalankan Backend Laravel
```bash
php artisan serve
```

---

## 🌐 Akses Aplikasi

- Frontend: `http://localhost:5173`
- Backend: `http://127.0.0.1:8000`

---

## 📁 Struktur Folder Penting

```
emolog/
├── app/
├── bootstrap/
├── config/
├── database/
├── public/
├── resources/
├── routes/
├── sentiment-analysis/
│   └── sentiment_api.py
├── storage/
├── tests/
├── .env
├── composer.json
├── package.json
└── README.md
```


## 📌 Catatan Tambahan

- Jika `php artisan serve` tidak otomatis menjalankan project, pastikan tidak ada port yang bentrok (default 8000).
- Disarankan menggunakan virtual environment untuk Python:
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/macOS
source venv/bin/activate
```

---

## 📝 Lisensi

Project ini hanya digunakan untuk keperluan pembelajaran dan non-komersial.

