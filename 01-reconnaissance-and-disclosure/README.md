# Reconnaissance & Vulnerability Disclosure

Dokumentasi ini berisi temuan kerentanan (*misconfiguration*) pada sistem milik Universitas Lampung. Seluruh pengujian dilakukan secara **pasif** (tanpa eksploitasi destruktif atau eksfiltrasi data massal) dan telah dilaporkan secara etis melalui portal CSIRT resmi kampus.

## Temuan 1: Information Disclosure & EOL Software (VClass)
- **Target**: `vclass.unila.ac.id`
- **Kategori**: Information Disclosure (CWE-200) / End of Life Component
- **Deskripsi**: File `upgrade.txt` dan `README.txt` dapat diakses publik, membocorkan bahwa sistem menggunakan Moodle versi 3.10.1. Versi ini telah mencapai *End of Life* (EOL) sejak Mei 2021 dan tidak lagi menerima *security patch*.
- **Dampak**: Penyerang dapat memetakan CVE lama yang belum ditambal.
- **Status**: Dilaporkan (Tiket: CSIRT-2026-0059).

## Temuan 2: Unauthenticated API Data Exposure (MyUnila)
- **Target**: `my.unila.ac.id`
- **Kategori**: Broken Access Control (CWE-284) / Data Exposure
- **Deskripsi**: Endpoint `/gateway/public-service/api/v1/search` dapat diakses tanpa autentikasi. Respons JSON mengembalikan data PII (Nama, NIM, Prodi) mahasiswa.
- **Dampak**: Memungkinkan penyerang melakukan enumerasi (scraping) data seluruh mahasiswa.
- **Status**: Dilaporkan (Tiket: CSIRT-2026-0060).
