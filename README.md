# landing-page-devops11

Deskripsi Proyek
Proyek ini bertujuan untuk membangun sebuah Landing Page statis (HTML/CSS) yang dideploy secara otomatis ke server VPS Ubuntu menggunakan Docker, serta dilengkapi dengan sistem CI/CD menggunakan Jenkins dan monitoring dengan Prometheus + Grafana. Website akan otomatis ter-update setiap kali terjadi push ke repository Git. Selain itu, seluruh performa server dan container dapat dimonitor secara real-time.

Teknologi yang Digunakan
1. Version Control	= Git + GitHub/GitLab
2. Web Server	= Docker + Nginx
3. CI/CD	= Jenkins 
4. Infrastruktur =	VPS (Ubuntu)
5. Monitoring =	Prometheus + Grafana

Pembagian tugas berdasarkan Role:
Project Lead
Tugas pertama kali dilakukan oleh Project Lead, yaitu:
 1. Menentukan ruang lingkup proyek, alur kerja (workflow), dan output
 2. Membuat folder repo Git (public/private) dan struktur direktori
 3. Menyusun dokumentasi awal (README.md, tugas masing-masing role)
 4. Menentukan stack teknologi: VPS, Docker, Jenkins, Prometheus, Grafana, dsb
 5. Menyusun timeline pengerjaan dan pembagian peran

Infrastructure Engineer
Mulai mengerjakan setelah Project Lead selesai merancang. Tugasnya:
1. Beli dan setup VPS (Ubuntu recommended)
2. Install Docker, Docker Compose, Jenkins, Prometheus, Grafana
3. Setup domain dan DNS (A record ke IP VPS)
 4. Konfigurasi jaringan, firewall, user, dan akses SSH
 5. Setup provisioning pakai Ansible/Terraform

Deployment Engineer
Setelah VPS siap dan domain aktif:
1. Buat Dockerfile untuk web statis (HTML/CSS)
2. Build Docker image dan run container di VPS
3. Tes akses web di domain/ip VPS
4. Memastikan volume/persistence bila diperlukan

CI/CD Engineer
Setelah Dockerfile & container sudah berhasil jalan secara manual:
1. Setup Jenkins pipeline
2. Konfig webhook dari repo Git (GitHub/GitLab)
3. Otomatiskan: git pull → docker build → container deploy
4. Cek validasi pipeline berhasil jalan tiap push ke repo

Monitoring Engineer
Setelah container berjalan:
1. Konfigurasi Prometheus (prometheus.yml) untuk scrape metrics
2. Tambahkan Nginx exporter (atau node_exporter) untuk web container
3. Setup Grafana dashboard, tambahkan Prometheus sebagai data source
4. Buat panel grafik: CPU, memory, request count, uptime
