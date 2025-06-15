# landing-page-devops11

Deskripsi Proyek,
Proyek ini bertujuan untuk membangun sebuah Landing Page statis (HTML/CSS) yang dideploy secara otomatis ke server VPS Ubuntu menggunakan Docker, serta dilengkapi dengan sistem CI/CD menggunakan Jenkins dan monitoring dengan Prometheus + Grafana. Website akan otomatis ter-update setiap kali terjadi push ke repository Git. Selain itu, seluruh performa server dan container dapat dimonitor secara real-time.

User flow:
[Landing Page (Home)]
       |
       +-- Klik "About"   --> [Halaman Tentang]
       +-- Klik "Product" --> [Halaman Produk]
       +-- Klik "Review"  --> [Halaman Penilaian Produk]
       +-- Klik "Contact" --> [Halaman Kontak]
       +-- Klik "Belanja Sekarang" --> [Halaman Produk]

Sitemap:
/
├── /tentang
├── /produk
├── /review
└── /kontak
       
Teknologi yang Digunakan :
1. Version Control	= Git + GitHub/GitLab
2. Web Server	= Docker + Nginx
3. CI/CD	= Jenkins 
4. Infrastruktur =	VPS (Ubuntu)
5. Monitoring =	Prometheus + Grafana

