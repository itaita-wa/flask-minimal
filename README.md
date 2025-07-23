# flask-minimal🎇

Proyek starter Flask minimalis yang dirancang untuk membantu kamu membuat aplikasi web dengan cepat, sederhana, dan efisien. Semua kode ada di satu file (`app.py`), dengan struktur template dan file statis dasar.

## Fitur 🎮
- Aplikasi Flask dalam satu file (`app.py`) agar sederhana dan mudah dikembangkan.
- Struktur template HTML dasar dengan styling dan JavaScript minimal.
- Setup proyek yang mudah dan tanpa ribet
- Mudah dikustomisasi untuk pengembangan aplikasi web yang cepat.

## Persiapan ⌨
```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip -y
```

## Instalasi ⚙

1. Clone repository:
   ```bash
   git clone https://github.com/yourusername/flask-minimal.git
   cd flask-minimal
   ```

2. Buat virtual environment (disarankan):
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Instal dependencies yang dibutuhkan:
   ```bash
   pip install -r requirements.txt
   ```

4.Jalankan aplikasi:
   ```bash
   python app.py
   ```

Aplikasi Flask akan berjalan dan bisa diakses lewat browser di http://localhost:5000

## Penggunaan 🖥

Proyek ini siap jadi dasar untuk membangun aplikasi web. Semua route dan logika ada di app.py, sehingga mudah dikembangkan dan dikustomisasi. Kamu bisa menambah template, route, atau file statis sesuai kebutuhan.

## Kustomisasi 🔧
Kamu bisa dengan mudah mengubah:

 -Struktur HTML di `templates/index.html`
 - Styling di `static/style.css`
 - Interaktivitas d `static/script.js`

Jangan ragu untuk mengubah app.py agar sesuai kebutuhan aplikasi kamu.

## 🔧 Setup Otomatis Agar Flask Jalan Saat Reboot (Langkah Sekali Saja)

Supaya aplikasi Flask ini otomatis berjalan setiap kali komputer/reboot instance Ubuntu, ikuti langkah berikut sekali saja:

1. Pastikan kamu sudah berada di folder proyek:
    ```bash
   cd ~/flask-minimal
    ```
2. Buat virtual environment dan install dependencies (jika belum):
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```
3. Buat file service systemd:
   ```bash
   sudo nano /etc/systemd/system/flaskapp.service
   ```
4. Isi dengan konfigurasi ini (sesuaikan path kalau perlu):
   ```
   [Unit]
   Description=Flask Minimal App
   After=network.target

   [Service]
   User=ubuntu
   WorkingDirectory=/home/ubuntu/flask-minimal
   ExecStart=/home/ubuntu/flask-minimal/venv/bin/python /home/ubuntu/flask-minimal/app.py
   Restart=always
   Environment=PATH=/home/ubuntu/flask-minimal/venv/bin

   [Install]
   WantedBy=multi-user.target
   ```
5. Reload systemd dan aktifkan service:
   ```bash
   sudo systemctl daemon-reload
   sudo systemctl enable flaskapp.service
   sudo systemctl start flaskapp.service
   ```
6. Cek status service:
   ```bash
   sudo systemctl status flaskapp.service
   ```
7. Selesai! Kini Flask app akan otomatis berjalan setiap reboot tanpa perlu dijalankan manual.

## Lisensi
Proyek ini dilisensikan di bawah MIT License.

## Kontribusi
Kalau kamu punya ide, perbaikan, atau fitur baru, jangan sungkan buat fork repository ini dan kirim pull request. Kalau ada saran atau pertanyaan, yuk bikin issue supaya kita bisa ngobrol dan saling berbagi.

## TERIMAKASIH JANGAN LUPA BERBAGI 🌟🎀


