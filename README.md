# Kontrol Mouse dengan Pelacakan Gerakan Tangan

**Dibuat oleh: Zufar Syaafi'**  
📧 Email: <zufar.syaafie@gmail.com>

---

## 📋 Daftar Isi

- [Pendahuluan](#pendahuluan)
- [Demo Video](#demo-video)
- [Fitur Utama](#fitur-utama)
- [Persyaratan Sistem](#persyaratan-sistem)
- [Instalasi](#instalasi)
- [Cara Penggunaan](#cara-penggunaan)
- [Gestur Tangan](#gestur-tangan)
- [Teknologi yang Digunakan](#teknologi-yang-digunakan)
- [Cara Kerja](#cara-kerja)
- [Kontribusi](#kontribusi)

---

## 🎯 Pendahuluan

Proyek ini merupakan implementasi sistem kontrol mouse virtual menggunakan teknologi computer vision dan machine learning. Dengan memanfaatkan gerakan tangan yang ditangkap melalui webcam, pengguna dapat mengontrol kursor mouse, melakukan klik, dan berbagai aksi lainnya tanpa menyentuh mouse fisik.

Sistem ini dikembangkan menggunakan Python dengan pustaka MediaPipe untuk deteksi tangan, OpenCV untuk pemrosesan video, dan PyAutoGUI untuk kontrol mouse otomatis.

---

## 🎥 Demo Video

Lihat demonstrasi cara kerja aplikasi di bawah ini:

[![Demo Video](https://img.shields.io/badge/▶️-Tonton%20Demo-red?style=for-the-badge)](image/demo.mp4)

---

## ✨ Fitur Utama

- **🖱️ Kontrol Kursor**: Gerakkan kursor dengan ujung jari telunjuk
- **👆 Klik Kiri**: Gesture khusus untuk klik kiri mouse
- **👆 Klik Kanan**: Gesture khusus untuk klik kanan mouse
- **⚡ Klik Ganda**: Gesture untuk double click
- **📸 Screenshot**: Ambil tangkapan layar dengan gesture
- **⏹️ Mode Stop**: Hentikan sementara tracking mouse
- **🎯 Real-time Processing**: Pemrosesan gerakan secara langsung
- **🔧 Sensitivitas Dapat Disesuaikan**: Kontrol sensitivitas gerakan mouse

---

## 💻 Persyaratan Sistem

### Perangkat Keras

- **Webcam**: Kamera yang berfungsi dengan baik
- **RAM**: Minimal 4GB (disarankan 8GB)
- **Processor**: CPU dual-core atau lebih tinggi

### Perangkat Lunak

- **Python**: Versi 3.8 atau lebih baru
- **Webcam Driver**: Driver kamera yang terinstal dengan benar
- **Sistem Operasi**: Windows 10/11, macOS, atau Linux

---

## 🚀 Instalasi

### 1. Clone Repository

```bash
git clone https://github.com/username/mouse-tracking.git
cd mouse-tracking
```

### 2. Buat Virtual Environment (Opsional tapi Disarankan)

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install opencv-python mediapipe pyautogui pynput numpy
```

Atau install menggunakan requirements file:

```bash
pip install -r requirements.txt
```

### 4. Jalankan Aplikasi

```bash
python mouse_tracking.py
```

Atau jalankan melalui Jupyter Notebook:

```bash
jupyter notebook mouse-tracking.ipynb
```

---

## 📖 Cara Penggunaan

1. **Jalankan Aplikasi**: Eksekusi script Python atau buka Jupyter Notebook
2. **Posisikan Tangan**: Letakkan tangan di depan kamera dengan jarak sekitar 30-50 cm
3. **Kalibrasi**: Pastikan tangan terdeteksi dengan baik (akan muncul garis landmark)
4. **Mulai Kontrol**: Gunakan berbagai gesture untuk mengontrol mouse
5. **Keluar**: Tekan tombol `Esc` untuk keluar dari aplikasi

### Tips Penggunaan

- Pastikan pencahayaan cukup untuk deteksi yang optimal
- Hindari background yang terlalu kompleks
- Gerakkan tangan dengan smooth dan tidak terlalu cepat
- Kalibrasi posisi tangan agar berada di center frame kamera

---

## 🤏 Gestur Tangan

Berikut adalah gesture yang dapat digunakan untuk mengontrol mouse:

### 1. 🖱️ Move Mouse (Gerakkan Kursor)

- **Gesture**: Jari telunjuk lurus, ibu jari menempel ke telunjuk
- **Fungsi**: Menggerakkan kursor mengikuti posisi ujung jari telunjuk
- **Indikator**: Teks "Move Mouse" berwarna biru

### 2. ⏹️ Stop (Berhenti)

- **Gesture**: Telapak tangan terbuka, semua jari lurus
- **Fungsi**: Menghentikan tracking mouse sementara
- **Indikator**: Tidak ada teks khusus

### 3. 👆 Left Click (Klik Kiri)

- **Gesture**: Jari telunjuk menekuk, jari tengah lurus, ibu jari terbuka
- **Fungsi**: Melakukan klik kiri mouse
- **Indikator**: Teks "Left Click" berwarna hijau

### 4. 👆 Right Click (Klik Kanan)

- **Gesture**: Jari telunjuk lurus, jari tengah menekuk, ibu jari terbuka
- **Fungsi**: Melakukan klik kanan mouse
- **Indikator**: Teks "Right Click" berwarna kuning-hijau

### 5. ⚡ Double Click (Klik Ganda)

- **Gesture**: Jari telunjuk dan tengah menekuk, ibu jari terbuka
- **Fungsi**: Melakukan double click
- **Indikator**: Teks "Double Click" berwarna kuning

### 6. 📸 Screenshot (Tangkapan Layar)

- **Gesture**: Jari telunjuk dan tengah menekuk, ibu jari menempel
- **Fungsi**: Mengambil screenshot dan menyimpan sebagai "screenshot.png"
- **Indikator**: Teks "Screenshot Taken" berwarna magenta

---

## 🛠️ Teknologi yang Digunakan

### Pustaka Python

- **OpenCV (cv2)**: Pemrosesan video dan computer vision
- **MediaPipe**: Deteksi dan tracking tangan real-time
- **PyAutoGUI**: Kontrol mouse dan keyboard otomatis
- **Pynput**: Kontrol input perangkat tingkat rendah
- **NumPy**: Komputasi numerik dan array

### Algoritma

- **Hand Landmark Detection**: 21 titik landmark untuk setiap tangan
- **Euclidean Distance**: Menghitung jarak antar titik landmark
- **Angle Calculation**: Menghitung sudut untuk deteksi gesture
- **Coordinate Mapping**: Konversi koordinat kamera ke koordinat layar

---

## ⚙️ Cara Kerja

### 1. **Capture Video**

Aplikasi mengakses webcam dan menangkap frame video secara real-time.

### 2. **Hand Detection**

MediaPipe mendeteksi tangan dan mengekstrak 21 landmark points.

### 3. **Gesture Recognition**

Sistem menghitung:

- Jarak antara titik landmark tertentu
- Sudut yang terbentuk antar titik landmark
- Kombinasi kondisi untuk mengenali gesture

### 4. **Action Execution**

Berdasarkan gesture yang terdeteksi, sistem menjalankan aksi:

- Gerakkan kursor
- Klik mouse
- Ambil screenshot

### 5. **Visual Feedback**

Memberikan feedback visual berupa:

- Landmark overlay pada tangan
- Teks indikator aksi
- Real-time video feed

---

## 🔧 Konfigurasi

### Mengubah Sensitivitas Mouse

Untuk mengubah sensitivitas gerakan mouse, edit nilai multiplier pada fungsi `move_mouse()`:

```python
def move_mouse(finger_tip):
    if finger_tip:
        # Ubah nilai 1.5 untuk mengatur sensitivitas
        x = int(finger_tip.x * screen_width * 1.5)  # Sensitivitas horizontal
        y = int(finger_tip.y * screen_height * 1.5) # Sensitivitas vertikal
        pyautogui.moveTo(x, y)
```

### Mengubah Threshold Deteksi

Untuk mengubah kepekaan deteksi gesture, edit nilai threshold:

```python
# Contoh: mengubah threshold jarak untuk gesture
def is_move_mouse(list_landmarks, thumb_dist):
    return (
        angle_between_points(list_landmarks[5], list_landmarks[6], list_landmarks[8]) > 90
        and thumb_dist < 15  # Ubah dari 10 ke 15 untuk sensitivitas lebih rendah
    )
```

---

## 🐛 Troubleshooting

### Masalah Umum

**1. Kamera tidak terdeteksi**

```bash
# Coba ganti index kamera
cap = cv2.VideoCapture(1)  # Ganti dari 0 ke 1
```

**2. Gesture tidak terdeteksi dengan baik**

- Pastikan pencahayaan cukup
- Posisikan tangan di center frame
- Hindari background yang kompleks

**3. Mouse bergerak terlalu sensitif**

```python
# Kurangi nilai multiplier sensitivitas
x = int(finger_tip.x * screen_width * 1.0)  # Dari 1.5 ke 1.0
```

**4. Delay terlalu lama saat klik**

```python
# Kurangi nilai delay
cv2.waitKey(200)  # Dari 500 ke 200
```

---

## 🤝 Kontribusi

Kontribusi sangat diterima! Berikut cara berkontribusi:

1. **Fork** repository ini
2. **Buat branch** untuk fitur baru (`git checkout -b feature/AmazingFeature`)
3. **Commit** perubahan (`git commit -m 'Add some AmazingFeature'`)
4. **Push** ke branch (`git push origin feature/AmazingFeature`)
5. **Buat Pull Request**

### Ide Pengembangan

- [ ] Dukungan multi-hand tracking
- [ ] Gesture kustom yang dapat dikonfigurasi
- [ ] GUI untuk pengaturan
- [ ] Dukungan gesture scroll
- [ ] Mode training untuk gesture baru
- [ ] Integrasi dengan aplikasi tertentu

---

## 👨‍💻 Tentang Pengembang

**Zufar Syaafi'** adalah seorang developer yang tertarik pada deep learning. Proyek ini dibuat sebagai eksplorasi teknologi MediaPipe dan aplikasinya dalam human-computer interaction.

📧 **Email**: zufar.syaafie@gmail.com  
🐙 **GitHub**: [@zufarsyaafie](https://github.com/zufarsyaafie)

---

## 🙏 Acknowledgments

- **MediaPipe Team** - Untuk framework hand tracking yang luar biasa
- **OpenCV Community** - Untuk library computer vision yang powerful
- **Python Community** - Untuk ecosystem yang mendukung pengembangan

---

## ⭐ Dukung Proyek Ini

Jika proyek ini bermanfaat untuk Anda, berikan ⭐ pada repository ini dan bagikan ke teman-teman!

**Terima kasih telah menggunakan Mouse Tracking dengan Pelacakan Gerakan Tangan! 🎉**
