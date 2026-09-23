# NAZE ENGINEERING STANDARD

**Document:** ENGINEERING_STANDARD.md
**Type:** Engineering Standard
**Status:** Active
**Authority:** Level 2
**Parent Document:** NAZE_CORE.md

---

## 1. Engineering Lifecycle

Standar lifecycle Naze diterapkan pada setiap proyek secara proporsional terhadap kompleksitasnya:

```
Requirement
    |
    v
Specification
    |
    v
Architecture
    |
    v
Implementation
    |
    v
Testing
    |
    v
Verification
    |
    v
Release
    |
    v
Monitoring
    |
    v
Maintenance
```

1. **Requirement** — menetapkan masalah yang harus diselesaikan dan batasnya.
2. **Specification** — mendefinisikan behavior dan acceptance criteria sebelum dibangun.
3. **Architecture** — menentukan struktur sistem yang sesuai dengan scope dan constraint.
4. **Implementation** — merealisasikan specification menjadi kode yang dapat diuji.
5. **Testing** — membuktikan behavior sesuai specification.
6. **Verification** — memastikan keseluruhan perubahan memenuhi requirement dan acceptance criteria.
7. **Release** — menyampaikan perubahan yang telah diverifikasi ke lingkungan penggunaan.
8. **Monitoring** — mengamati perilaku sistem setelah release.
9. **Maintenance** — memperbaiki, memperbarui, dan mengelola teknikal debt sepanjang umur sistem.

Aturan mutlak: **implementation tidak boleh menggantikan specification.** Kode yang berjalan bukanlah definisi; specification adalah definisi, kode adalah realisasinya.

## 2. Requirement Standard

Requirement harus:

1. Jelas dan dapat dipahami oleh pihak yang membacanya.
2. Dapat diverifikasi — ada cara objektif untuk membuktikan requirement terpenuhi.
3. Memiliki scope yang eksplisit, termasuk apa yang berada di luar scope.
4. Tidak ambigu — satu pembaca tidak boleh menarik dua kesimpulan berbeda.
5. Dapat ditelusuri ke specification, implementation, dan testing.

Tiga hal yang wajib dibedakan dan tidak boleh dicampur:

- **Requirement** — apa yang dibutuhkan dan mengapa.
- **Specification** — bagaimana sistem harus berperilaku untuk memenuhi requirement.
- **Implementation** — bagaimana specification direalisasikan dalam kode.

Requirement yang tertanam hanya di dalam kode, atau specification yang diklaim "sudah ada di requirement", adalah pelanggaran standar ini.

## 3. Specification Standard

Setiap proyek dengan kompleksitas signifikan wajib memiliki specification sebelum implementation besar dimulai. Specification minimal menjelaskan:

1. Tujuan.
2. Scope.
3. Behavior.
4. Constraints.
5. Dependencies.
6. Security requirements.
7. Acceptance criteria.

Setiap perubahan pada specification wajib terdokumentasi — specification yang berubah diam-diam mengakibatkan specification drift dan membatalkan traceability.

## 4. Architecture Standard

Architecture menjelaskan struktur sistem sebelum implementation besar dilakukan. Pertimbangan minimal:

- **Components** — unit-unit utama dan tanggung jawabnya.
- **Data Flow** — pergerakan data melalui sistem.
- **Dependencies** — komponen internal dan eksternal yang diandalkan.
- **Interfaces** — batas interaksi antar komponen.
- **External Services** — layanan pihak ketiga yang digunakan.
- **Storage** — tempat data disimpan dan persistennya.
- **Security Boundaries** — batas kepercayaan dan titik kontrol akses.
- **Failure Points** — bagian yang rentan gagal dan dampaknya.

Architecture harus proporsional terhadap kompleksitas proyek. Memaksakan architecture kompleks pada proyek sederhana adalah pelanggaran prinsip kesederhanaan NAZE_CORE.md.

## 5. Coding Principles

1. **Readability** — kode ditulis untuk dibaca manusia.
2. **Maintainability** — kode mudah diubah tanpa efek tak terduga.
3. **Modularity** — sistem tersusun dari unit yang jelas batasnya.
4. **Separation of Concerns** — satu unit memiliki satu alasan untuk berubah.
5. **Minimal Complexity** — kompleksitas hanya ditambahkan ketika masalah menuntut.
6. **Consistent Naming** — nama mencerminkan maksud dan konsisten di seluruh codebase.
7. **Explicit Error Handling** — error ditangani secara eksplisit, bukan diabaikan.
8. **Avoidance of Unnecessary Duplication** — logika yang sama tidak ditulis berulang tanpa alasan.

Aturan style yang lebih spesifik ditetapkan pada level proyek hanya ketika dibutuhkan.

## 6. Dependency Management

Setiap dependency harus memiliki alasan penggunaan yang dapat dijelaskan. Standar minimal:

1. Hindari dependency yang tidak diperlukan.
2. Gunakan versi yang dapat dilacak (pinned/tercatat, bukan floating).
3. Evaluasi keamanan dependency — termasuk kondisi maintenance dan riwayat vulnerability — sebelum dan selama digunakan.
4. Hapus dependency yang sudah tidak digunakan.
5. Dokumentasikan dependency penting beserta alasannya.
6. Jangan menambahkan library hanya untuk masalah sederhana jika solusi internal lebih tepat dan aman.

## 7. Configuration & Secrets

Tiga hal wajib dipisahkan:

- **Source Code** — logika.
- **Configuration** — nilai yang bervariasi antar environment.
- **Secrets** — nilai yang harus dirahasiakan.

Secret tidak boleh disimpan di source code atau Git repository. Contoh secret:

- API Keys
- Passwords
- Tokens
- Private Keys
- Database Credentials
- Service Credentials

Gunakan environment variables atau secret management yang sesuai dengan environment proyek. Tidak ada satu secret manager tertentu yang diwajibkan secara global.

## 8. Error Handling

Setiap aplikasi wajib menangani error secara eksplisit. Standar:

1. Jangan menyembunyikan error.
2. Jangan menggunakan error message yang menyesatkan.
3. Jangan membocorkan secret atau data sensitif melalui error.
4. Error harus dapat ditelusuri ketika diperlukan.
5. User-facing error harus dibedakan dari internal diagnostic information jika konteks menuntut.

## 9. Testing Standard

Jenis testing yang dikenal dan dipilih berdasarkan risk dan complexity proyek:

- **Unit Test** — membuktikan unit terkecil berperilaku benar secara terisolasi.
- **Integration Test** — membuktikan komponen bekerja bersama dengan benar.
- **System Test** — membuktikan sistem utuh memenuhi behavior yang ditetapkan.
- **End-to-End Test** — membuktikan alur pengguna nyata bekerja dari awal sampai akhir.
- **Regression Test** — mencegah perbaikan yang merusak perilaku yang sudah benar.

Tidak semua proyek harus memiliki semua jenis test. Setiap test harus berhubungan dengan requirement yang dapat diidentifikasi; test tanpa kaitan requirement adalah test tanpa tujuan.

## 10. Verification

Testing dan Verification dibedakan:

- **Testing** — membuktikan behavior tertentu melalui test yang didefinisikan.
- **Verification** — memastikan perubahan secara keseluruhan memenuhi requirement, specification, security expectation, dan acceptance criteria.

Fitur tidak boleh dinyatakan verified hanya karena aplikasi berhasil dijalankan. Berjalan bukan bukti benar.

## 11. Code Review

Prinsip code review:

1. Perubahan yang memiliki risiko wajib direview.
2. Review berfokus pada correctness, security, maintainability, dan consistency.
3. Review tidak boleh hanya memeriksa formatting.
4. Perubahan besar harus disertai konteks dan alasan yang jelas.
5. Temuan penting harus diselesaikan atau dicatat secara eksplisit.

## 12. Git & Version Control

Git adalah sistem version control Naze. Standar:

1. Commit harus dapat dipahami — message menjelaskan apa dan mengapa.
2. Perubahan harus dapat dilacak dari commit ke commit.
3. Secret tidak boleh masuk ke repository.
4. Hindari commit yang tidak berkaitan dengan task yang sedang dikerjakan.
5. Perubahan besar harus mudah direview.
6. History harus cukup jelas untuk memahami evolusi sistem.

Tidak ada Git branching strategy tertentu yang dipaksakan pada seluruh proyek tanpa kebutuhan; strategi dipilih per proyek sesuai risiko dan ukuran tim.

## 13. Change Management

Perubahan diklasifikasikan berdasarkan dampak:

- **Minor Change** — dampak lokal, risiko rendah.
- **Major Change** — dampak luas pada satu sistem.
- **Architecture Change** — mengubah struktur atau batas sistem.
- **Breaking Change** — membatalkan kompatibilitas dengan perilaku atau antarmuka sebelumnya.
- **Security-Sensitive Change** — menyentuh security boundary, autentikasi, otorisasi, data sensitif, atau secret.

Setiap perubahan dievaluasi terhadap: Requirement, Specification, Architecture, Testing, Security, dan Documentation. Semakin tinggi klasifikasi dampak, semakin ketat proses evaluasinya.

## 14. Technical Debt

Technical debt diakui dan dicatat, tidak disembunyikan. Kategori yang wajib tercatat ketika ada:

- **Known Bug** — cacat yang diketahui dan belum diperbaiki.
- **Temporary Workaround** — solusi sementara beserta rencana penyelesaiannya.
- **Incomplete Implementation** — bagian yang belum selesai dengan status jelas.
- **Deprecated Component** — komponen yang tidak lagi digunakan dan menunggu penghapusan.
- **Architecture Limitation** — keterbatasan desain yang diketahui.
- **Missing Test** — area tanpa test yang seharusnya ada.

Setiap entri technical debt memiliki status yang jelas. Technical debt yang disembunyikan adalah hidden technical debt — sebuah anti-pattern (bagian 19).

## 15. Documentation

Dokumentasi teknis harus:

1. Akurat — menggambarkan kondisi nyata.
2. Relevan — menjawab kebutuhan pembacanya.
3. Dapat dipelihara — tidak menuntut biaya tak terkendali untuk diperbarui.
4. Konsisten dengan implementation.
5. Memiliki ownership yang jelas — ada pihak yang bertanggung jawab menjaganya.

Jika implementation berubah secara signifikan, dokumentasi terkait wajib diperiksa pada perubahan yang sama, bukan "nanti".

## 16. AI-Assisted Development

AI development mengikuti kebijakan pada NAZE_CORE.md. AI dapat membantu: Analysis, Planning, Coding, Testing, Documentation, Debugging, dan Review.

Setiap output AI wajib diverifikasi. AI tidak boleh:

1. Mengubah requirement secara diam-diam.
2. Menghapus security control tanpa approval.
3. Mengubah architecture tanpa review.
4. Menyatakan test berhasil tanpa evidence.
5. Membuat data atau fakta yang tidak diketahui.
6. Menganggap compile success sebagai verification.

## 17. Definition of Done

Perubahan tidak dianggap selesai hanya karena implementation selesai. Pertimbangan minimal:

- Requirement satisfied
- Specification satisfied
- Implementation completed
- Tests completed
- Verification completed
- Security reviewed
- Documentation updated
- Known issues recorded

Tidak semua item identik untuk setiap perubahan; tingkat verification harus proporsional terhadap risk.

## 18. Quality Gates

Quality gate sebelum release, minimal:

1. **Specification Gate** — specification ada, jelas, dan mutakhir.
2. **Implementation Gate** — implementasi sesuai specification dan coding principles.
3. **Testing Gate** — test yang relevan lulus dan terkait requirement.
4. **Security Gate** — security expectation diperiksa, termasuk secret handling.
5. **Verification Gate** — acceptance criteria terpenuhi secara keseluruhan.
6. **Release Gate** — perubahan siap dirilis dengan dokumentasi dan catatan yang lengkap.

Gate dapat disederhanakan untuk perubahan berisiko rendah dan diperketat untuk perubahan berisiko tinggi. Meniadakan gate sepenuhnya tanpa alasan risiko yang terdokumentasi tidak diperbolehkan.

## 19. Engineering Anti-Patterns

Anti-pattern yang secara eksplisit diperingatkan:

- **Coding Before Specification** — menulis kode sebelum behavior didefinisikan, membuat kode menjadi spesifikasi de facto.
- **Unverified AI Output** — menerima hasil AI tanpa review, membawa risiko kebutuhan berubah diam-diam dan klaim tanpa bukti.
- **Hidden Technical Debt** — menyembunyikan bug, workaround, atau bagian yang belum selesai, menyebabkan keputusan dibangun di atas informasi yang salah.
- **Unnecessary Complexity** — kompleksitas tanpa masalah yang menuntutnya, meningkatkan biaya pemeliharaan dan risiko cacat.
- **Dependency Bloat** — menumpuk dependency tanpa alasan, memperluas permukaan serangan dan beban pemeliharaan.
- **Secret Leakage** — secret di source code atau repository, memberi akses tidak sah pada siapa pun yang memiliki riwayat Git.
- **Documentation Drift** — dokumentasi yang berhenti mencerminkan implementation, menyesatkan pembacanya.
- **Specification Drift** — specification yang berubah tanpa jejak, memutus traceability dan validasi.
- **False Verification** — menyatakan verified tanpa bukti terhadap requirement dan acceptance criteria.

## 20. Traceability

Hubungan yang wajib dapat ditelusuri:

```
Requirement
    |
    v
Specification
    |
    v
Implementation
    |
    v
Test
    |
    v
Verification
```

Tujuannya: setiap perubahan dapat ditelusuri dari alasan awal (requirement) sampai hasil akhirnya (verification), dan sebaliknya. Ketika satu mata rantai hilang, perubahan tidak dapat dipertanggungjawabkan secara utuh.

## 21. Standard Hierarchy

Dokumen ini adalah **Level 2** dan tunduk kepada **Level 1: NAZE_CORE.md**.

Jika terdapat konflik dengan NAZE_CORE.md, NAZE_CORE.md memiliki authority lebih tinggi dan dokumen ini wajib diperbaiki sesuai aturan konflik pada NAZE_CORE.md bagian 19. Tidak ada aturan pada dokumen ini yang boleh bertentangan dengan foundation.

## 22. Scope Control

Dokumen ini adalah engineering standard umum. Hal-hal berikut tidak termuat di sini dan harus ditentukan pada dokumen yang sesuai ketika diperlukan:

- Specific Product Architecture
- Specific Database Schema
- Specific API Design
- Specific Programming Language
- Specific Cloud Provider
- Specific UI Design
- Company Legal Structure

## 23. Applicability

Standar ini berlaku untuk seluruh proyek engineering di bawah Naze. Setiap proyek boleh menambahkan standar yang lebih ketat sesuai kebutuhannya, tetapi tidak boleh menurunkan standar di bawah dokumen ini tanpa melalui proses change management yang terdokumentasi.

## 24. Maintenance of This Standard

Perubahan pada dokumen ini mengikuti change management NAZE_CORE.md bagian 13 dengan klasifikasi dampak sesuai bagian 13 dokumen ini. Dokumen ini ditinjau ketika: standar turunannya bertentangan, anti-pattern baru teridentifikasi berulang, atau kebutuhan proyek menuntut perubahan standar umum.

---

**End of ENGINEERING_STANDARD.md**
