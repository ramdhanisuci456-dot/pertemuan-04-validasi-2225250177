# Pertemuan 04 Seleksi Multi-Kondisi dan Validasi Input

**Nama:** Suci Ramadhani
**NIM:**  2225250177
**Kelas:** 3B

## Tujuan

Membangun program validasi dan klasifikasi dengan rantai `if-elif-else`.

## Cara Menjalankan

Program dapat dijalankan melalui terminal VS Code dengan perintah:

```bash
python3 praktik/validasi_klasifikasi_nilai.py
```

## Tabel Keputusan

| Kategori                        | Syarat                                        | Contoh Masukan |
| ------------------------------- | --------------------------------------------- | -------------- |
| Data tidak valid                | Data yang dimasukkan bukan angka              | `abc`          |
| Nilai ujian tidak valid         | Nilai ujian kurang dari 0 atau lebih dari 100 | `105`          |
| Nilai tugas tidak valid         | Nilai tugas kurang dari 0 atau lebih dari 100 | `-5`           |
| Kehadiran tidak valid           | Kehadiran kurang dari 0 atau lebih dari 100   | `110`          |
| Kehadiran tidak memenuhi syarat | Kehadiran kurang dari 80%                     | `90, 90, 75`   |
| Predikat A                      | Nilai akhir ≥ 85 dan kehadiran ≥ 80%          | `90, 90, 90`   |
| Predikat B                      | Nilai akhir ≥ 70 dan < 85                     | `80, 80, 80`   |
| Predikat C                      | Nilai akhir ≥ 60 dan < 70                     | `65, 65, 80`   |
| Predikat D                      | Nilai akhir ≥ 50 dan < 60                     | `55, 55, 80`   |
| Predikat E                      | Nilai akhir < 50                              | `40, 40, 80`   |

## Hasil Pengujian

| No. | Masukan                           | Keluaran yang Diharapkan | Keluaran Aktual         | Status   |
| --- | --------------------------------- | ------------------------ | ----------------------- | -------- |
| 1   | Ujian 90, Tugas 90, Kehadiran 90  | Predikat A, Lulus        | Predikat A, Lulus       | Berhasil |
| 2   | Ujian 80, Tugas 80, Kehadiran 80  | Predikat B, Lulus        | Predikat B, Lulus       | Berhasil |
| 3   | Ujian 65, Tugas 65, Kehadiran 80  | Predikat C, Lulus        | Predikat C, Lulus       | Berhasil |
| 4   | Ujian 55, Tugas 55, Kehadiran 80  | Predikat D, Belum lulus  | Predikat D, Belum lulus | Berhasil |
| 5   | Ujian 90, Tugas 90, Kehadiran 75  | Predikat E, Belum lulus  | Predikat E, Belum lulus | Berhasil |
| 6   | Ujian 105, Tugas 80, Kehadiran 90 | Masukan ditolak          | Masukan ditolak         | Berhasil |
| 7   | Ujian abc, Tugas 80, Kehadiran 90 | Masukan ditolak          | Masukan ditolak         | Berhasil |

## Refleksi

Salah satu masukan tidak valid yang semula dapat terlewat adalah nilai yang berada di luar rentang 0 sampai 100, misalnya nilai ujian 105. Masukan tersebut ditangani dengan menambahkan validasi agar nilai ujian, tugas, dan kehadiran harus berada pada rentang 0 sampai 100 sebelum diproses.
