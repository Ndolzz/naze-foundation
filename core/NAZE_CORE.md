# NAZE CORE

**Document:** NAZE_CORE.md
**Type:** Foundation Document
**Status:** Core â Active
**Authority:** Level 1 (Highest)

---

## 1. Naze Identity

Naze adalah nama inisiatif yang mencakup seluruh produk, standar, dan praktik engineering yang dikembangkan di bawah satu identitas yang sama. Pada tahap ini, Naze belum ditetapkan sebagai entitas legal tertentu; status hukumnya akan didefinisikan secara eksplisit ketika keputusan tersebut telah dibuat. Dokumen ini tidak membuat klaim legal atas bentuk usaha apa pun.

## 2. Purpose

Tujuan dokumen ini adalah menjadi fondasi tunggal yang mendefinisikan identitas, arah, prinsip, dan standar Naze. Seluruh dokumen turunan â standar engineering, standar produk, standar keamanan, dan dokumentasi produk individu â wajib konsisten dengan dokumen ini.

## 3. Vision

Membangun produk yang berkualitas, dapat dipercaya, dan tahan lama â produk yang dibangun di atas fondasi yang jelas, bukan improvisasi.

## 4. Mission

1. Mendefinisikan prinsip dan standar sebelum membangun produk.
2. Menjaga konsistensi antara fondasi, standar, dan implementasi.
3. Mengembangkan produk dengan disiplin engineering yang tinggi dan dokumentasi yang akurat.

## 5. Core Principles

1. **Fondasi sebelum produk.** Standar didefinisikan lebih dulu; implementasi mengikuti standar.
2. **Satu sumber kebenaran.** NAZE_CORE.md adalah acuan tertinggi; dokumen turunan tidak boleh bertentangan dengannya.
3. **Konsistensi.** Dokumen, keputusan, dan implementasi harus selaras satu sama lain.
4. **Kesederhanaan.** Bangun hanya apa yang diperlukan, pada saat diperlukan.
5. **Kejujuran dokumentasi.** Dokumen tidak mengklaim sesuatu yang belum ada atau belum diputuskan.

## 6. Product Philosophy

Produk Naze dibangun untuk menyelesaikan masalah nyata dengan cakupan yang jelas. Produk tidak didefinisikan ooeh jumlah fitur, melainkan oleh kualitas, kejelasan batas, dan kemampuan dipelihara dalam jangka panjang. Keputusan fitur mengikuti kebutuhan yang terverifikasi, bukan asumsi.

## 7. Engineering Philosophy

1. **Spesifikasi sebelum implementasi.** Tidak ada implementasi tanpa definisi yang jelas.
2. **Kualitas sebelum kecepatan.** Kecepatan yang mengorbankan kualitas dianggap sebagai utang yang harus dibayar.
3. **Perubahan terkontrol.** Semua perubahan pada fondasi dan standar melalui proses yang terdokumentasi.
4. **Revision yang dapat ditelusuri.** Riwayat perubahan harus dapat diperiksa melalui Git.

## 8. AI Development Policy

Penggunaan AI dalam pengembangan Naze diizinkan sebagai alat bantu, dengan batasan berikut:

1. AI tidak menggantikan tanggung jawab keputusan; keputusan tetap milik manusia yang bertanggung jawab.
2. Output AI wajib ditinjau sebelum dianggap benar.
3. AI tidak boleh mengarang informasi, struktur, atau keputusan yang belum ditetapkan.
4. AI tidak boleh diminta untuk melewati proses spesifikasi dan review.
5. Seluruh hasil bantuan AI tunduk pada standar kualitas yang sama dengan pekejjaan manusia.

## 9. Specification Integrity

1. Implementasi wajib mengikuti spesifikasi; ketidaksesuaian adalah cacat.
2. Spesifikasi yang tidak lagi relevan wajib diperbarui secara eksplisit, bukan dibiarkan usang.
3. Placeholder pada bagian foundation utama tidak diperbolehkan.
4. Setiap dokumen harus mencantumkan status dan tingkat otoritasnya.

## 10. Security Principles

1. Keamanan dipertimbangkan sejak perancangan (secure by design), bukan ditambahkan belakangan.
2. Prinsip akses minimum (least privilege) berlaku untuk seluruh sistem.
3. Data pengguna diperlakukan sebagai aset yang harus dilindungi.
4. Standar keamanan teknis yang rinci akan didefinisikan pada dokumen turunan Security Standards, konsisten dengan dokumen ini.

## 11. Product Structure

Pada tahap ini, belum ada produk individu yang ditetapkan. Struktur produk akan didefinisikan ketika produk pertama mulai dikembangkan, dengan struktur sebagai berikut:

```
NAZE_CORE
    â
Engineering Standards
    â
Product Standards
    â
Security Standards
    â
Individual Products
```

Setiap produk individu wajib merujuk pada seluruh lapisan di_atasnya.

## 12. Repository Principles

1. `naze-foundation` adalah repository pusat untuk dokumentasi fondasi â bukan aplikasi, bukan produk pengguna.
2. Repository ini tidak memuat source code aplikasi, database, API, authentication, deployment, CI/CD, atau aset visual pada tahap ini.
3. Setiap dokumen memiliki satu tanggung jawab yang jelas; duplikasi diperbolehkan, dokumen yang tumpang tindih tidak.
4. Struktur repository hanya berkembang ketika ada kebutuhan nyata yang terdokumentasi.

## 13. Change Management

1. Perubahan pada dokumen Level 1 (NAZE_CORE.md) memerlukan pertimbangan khusus karena berdampak pada seluruh dokumen turunan.
2. Setiap perubahan harus dapat diperiksa melalui Git diff.
3. Perubahan yang bertentangan dengan dokumen turunan wajib disertai peninjauan dokumen turunan tersebut.
4. Penambahan dokumen baru hanya dilakukan ketika kebutuhannya nyata dan konsisten dengan struktur fondasi.

## 14. Quality Standard

1. **Akurasi.** Dokumen hanya memuat informasi yang benar dan telah diputuskan.
2. **Konsistensi.** Heading, istilah, dan struktur konsisten di seluruh dokumen.
3. **Kelengkapan.** Bagian foundation utama tidak boleh kosong atau berupa placeholder.
4. **Keterlacakan.** Setiap perubahan dapat ditelusuri melalui riwayat Git.

## 15. Decision Framework

Ketika menghadapi keputusan yang belum terdefinisi:

1. Periksa apakah jawabannya ada di dokumen ini atau dokumen turunan.
2. Jika tidak ada, jangan mengarang â tandai sebagai keputusan yang harus dibuat.
3. Keputusan baru harus dicatat pada dokumen yang tepat, bukan hanya dalam ingatan atau percakapan.
4. Utamakan keputusan yang dapat dibalik (reversible) dan bertahap, dibanding keputusan besar yang sulit diubah.

## 16. Ownership

Status kepemilikan formal Naze belum ditetapkan pada tahap ini dan akan didefinisikan ketika struktur legal dan organisasinya diputuskan. Sementara itu, tanggung jawab atas dokumen fondasi ini dipegang oleh penderi inisiatif Naze, dan semua perubahan berlangsung melalui proses perubahan yang terdokumentasi pada bagian 13.

## 17. Long-Term Direction

Arah jangka panjang Naze adalah tumbuh dari fondasi yang disiplin menuju kumpulan produk yang matang, dengan standar yang stabil dan dapat diwariskan antar orang dan antar waktu. Dokumen ini dirancang agar tetap relevan ketika produk, tim, dan teknologi di sekelilingnya berubah.

## 18. Core Rule

**Jangan membangun di atas asumsi. Bangun di atas definisi.** Setiap elemen Naze â produk, standar, maupun keputusan â harus memiliki dasar yang terdokumentasi dan konsisten dengan dokumen ini.

## 19. Document Authority

| Level | Document | Authority |
|-------|----------|-----------|
| 1 | NAZE_CORE.md | Tertinggi â acuan seluruh dokumen |
| 2 | Engineering / Product / Security Standards | Turunan â wajib konsisten dengan Level 1 |
| 3 | Individual Product Documents | Turunan â wajib konsisten dengan Level 1 dan 2 |

Dokumen dengan level lebih rendah tidak dapat meniadakan dokumen dengan level lebih tinggi. Konflik antar dokumen diselesaikan dengan merujuk pada level tertinggi, lalu memperbaiki dokumen yang bertentangan.

---

**End of NAZE_CORE.md**
