# Lab Environment Setup

Dokumentasi setup lab Red Team lokal menggunakan Docker di Arch Linux untuk memastikan pengujian dilakukan di lingkungan yang terisolasi.

## Komponen Lab
- **Attacker Machine**: Container Kali Linux (`kalilinux/kali-rolling`).
- **Target Machine**: Container DVWA (`vulnerables/web-dvwa`).
- **Network**: Docker bridge network terisolasi.

## Deployment
```bash
docker compose up -d
docker exec -it rl-kali bash
