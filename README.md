Deskripsi Proyek Proyek ini bertujuan untuk membangun sebuah Landing Page statis (HTML/CSS) yang dideploy secara otomatis ke server VPS Ubuntu menggunakan Docker, serta dilengkapi dengan sistem CI/CD menggunakan Jenkins dan monitoring dengan Prometheus + Grafana. Website akan otomatis ter-update setiap kali terjadi push ke repository Git. Selain itu, seluruh performa server dan container dapat dimonitor secara real-time melalui dashboard.

Proyek ini menggunakan berbagai teknologi pendukung untuk memastikan sistem berjalan secara otomatis dan dapat dimonitor dengan baik. Sistem version control dikelola menggunakan Git yang terhubung ke GitHub atau GitLab. Untuk proses deployment dan pengemasan aplikasi, digunakan Docker dan Nginx sebagai web server untuk menampilkan halaman statis. Infrastruktur dijalankan pada VPS berbasis Ubuntu, dengan opsi provisioning otomatis menggunakan Ansible atau Terraform. Proses CI/CD ditangani oleh Jenkins yang akan membangun dan mendeploy aplikasi setiap kali terjadi perubahan pada repo. Untuk pemantauan performa, digunakan Prometheus sebagai sistem monitoring dan Grafana sebagai visualisasi data. Domain publik dikonfigurasi menggunakan pengaturan DNS A Record.

User Flow: 
[Landing Page (Home)] | +-- Klik "About" --> [Halaman Tentang] +-- Klik "Product" --> [Halaman Produk] +-- Klik "Review" --> [Halaman Penilaian Produk] +-- Klik "Contact" --> [Halaman Kontak] +-- Klik "Belanja Sekarang" --> [Halaman Produk]

Sitemap:
/
├── /about       → Halaman Tentang
├── /product     → Halaman Produk
├── /review      → Halaman Ulasan Pelanggan
├── /contact     → Halaman Kontak
