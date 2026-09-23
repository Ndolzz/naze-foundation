# NAZE DOCUMENTATION STANDARD

**Document:** DOCUMENTATION_STANDARD.md
**Type:** Documentation Standard
**Status:** Active
**Authority:** Level 2
**Parent Document:** NAZE_CORE.md

---

## 1. Documentation Philosophy

Dokumentasi Naze harus:

1. Akurat — menggambarkan kondisi yang sebenarnya.
2. Jelas — dapat dipahami oleh pembaca yang dituju.
3. Dapat ditemukan — orang yang membutuhkannya bisa menemukannya.
4. Dapat diverifikasi — klaimnya dapat diperiksa.
5. Memiliki konteks — menjelaskan mengapa, bukan hanya apa.
6. Memiliki ownership yang jelas — ada pihak yang bertanggung jawab.
7. Mencerminkan kondisi sistem yang sebenarnya.
8. Diperbarui ketika keputusan atau implementasi berubah.

Dokumentasi bukan sekadar formalitas, dan tidak boleh digunakan untuk membuat sistem terlihat lebih lengkap daripada kondisi sebenarnya.

## 2. Documentation Hierarchy

Dokumentasi Naze tersusun berdasarkan authority:

- **Level 1** — `core/NAZE_CORE.md`: fondasi seluruh Naze.
- **Level 2** — `standards/`: standar lintas produk (Engineering, Security, Product, Documentation).
- **Level 3** — Product/System Documentation: dokumentasi setiap produk atau sistem.
- **Level 4** — Implementation Documentation: dokumentasi detail implementasi (kode, konfigurasi, prosedur teknis).

Dokumen pada level lebih rendah tidak boleh bertentangan dengan dokumen pada level lebih tinggi. Jika terdapat konflik, konflik harus diidentifikasi dan diselesaikan melalui proses change management yang sesuai — pada Level 1 mengikuti NAZE_CORE.md bagian 13; pada level lain mengikuti change management ENGINEERING_STANDARD.md bagian 13.

## 3. Source of Truth

Setiap fakta penting harus memiliki satu sumber kebenaran yang jelas untuk:

- Product Requirements
- Architecture
- Engineering Rules
- Security Rules
- API Contracts
- Configuration
- Operational Procedures
- Release Information
- Decisions

Jangan membuat dua dokumen berbeda yang mendefinisikan fakta yang sama tanpa alasan yang jelas. Jika informasi yang sama harus muncul di beberapa tempat, tentukan dokumen utama dan gunakan referensi ke dokumen tersebut.

## 4. Documentation Types

Jenis dokumentasi yang digunakan Naze beserta tujuannya:

- **README** — pintu masuk: apa itu, untuk apa, dan ke mana harus pergi selanjutnya.
- **Product Documentation** — mendefinisikan produk: tujuan, pengguna, scope, dan nilai.
- **Requirements** — mencatat apa yang dibutuhkan dan mengapa.
- **Specifications** — mendefinisikan behavior yang diharapkan dari sistem.
- **Architecture Documentation** — menjelaskan struktur dan batasan sistem.
- **API Documentation** — mendefinisikan kontrak antarmuka sistem.
- **Security Documentation** — mencatat keputusan dan kontrol keamanan.
- **Operational Documentation** — menjelaskan cara sistem dijalankan dan dipelihara.
- **Setup Documentation** — menjelaskan cara menyiapkan lingkungan kerja atau sistem.
- **Testing Documentation** — mencatat strategi, kasus, dan hasil pengujian.
- **Release Notes** — merangkum perubahan pada suatu rilis.
- **Changelog** — mencatat perubahan secara berurutan waktu.
- **Decision Records** — mendokumentasikan keputusan penting beserta alasannya.
- **Migration Documentation** — menjelaskan perpindahan antar versi atau sistem.
- **Troubleshooting Documentation** — membantu mendiagnosis dan memperbaiki masalah.

## 5. Document Structure

Dokumen menggunakan struktur yang sesuai dengan tujuan dan kompleksitasnya. Jika relevan, gunakan:

- Title
- Purpose
- Scope
- Context
- Requirements
- Decisions
- Implementation Reference
- Validation
- Limitations
- Known Issues
- Related Documents
- Change History

Tidak semua dokumen harus memakai seluruh bagian tersebut — struktur dipilih sesuai kebutuhan.

## 6. Document Metadata

Dokumen penting memiliki metadata yang memadai, minimal bila relevan:

- Document Name
- Status
- Authority
- Owner
- Version
- Created Date
- Updated Date
- Parent Document
- Related Documents

Jangan mengisi metadata dengan informasi yang belum diketahui. Nama owner, tanggal, versi, atau status tidak boleh dibuat secara fiktif — kosong atau "belum ditetapkan" lebih jujur daripada karangan.

## 7. Document Status

Status dokumentasi yang digunakan:

- **Draft** — sedang ditulis; belum menjadi referensi yang dapat diandalkan. Dokumen Draft tidak boleh dianggap sebagai source of truth final.
- **Review** — sedang ditinjau; isinya dianggap usulan, bukan keputusan.
- **Active** — disetujui dan menjadi referensi yang berlaku.
- **Deprecated** — tidak lagi direkomendasikan; tidak boleh digunakan sebagai referensi utama untuk keputusan baru.
- **Archived** — tidak lagi berlaku; disimpan hanya untuk konteks historis.

## 8. Document Authority

Authority dipisahkan menjadi:

- **Document Authority** — tingkat kekuatan sebuah dokumen dalam hierarki dokumentasi (Level 1–4).
- **Technical Authority** — kewenangan atas keputusan teknis, mengikuti ownership teknis produk.
- **Product Authority** — kewenangan atas arah produk, mengikuti Product Ownership pada PRODUCT_STANDARD.md.
- **Operational Ownership** — tanggung jawab atas operasional sistem (prosedur, rilis, monitoring).
- **Legal Ownership** — status kepemilikan legal, yang pada tahap ini belum ditetapkan untuk Naze (NAZE_CORE.md bagian 16).

Dokumen tidak otomatis menjadi bukti kepemilikan legal hanya karena menyatakan ownership. Authority dijelaskan dalam konteks governance Naze, bukan klaim hukum.

## 9. Requirements Documentation

Requirements harus:

1. Jelas.
2. Spesifik.
3. Dapat diverifikasi.
4. Memiliki konteks.
5. Dapat ditelusuri.
6. Memiliki status jika diperlukan.

Requirements tidak boleh dibuat berdasarkan asumsi yang tidak diketahui. Jika requirement belum pasti, tandai sebagai unresolved atau pending decision daripada mengarang jawaban.

## 10. Specification Documentation

Specification menjelaskan bagaimana requirement diterjemahkan menjadi sistem yang dapat diimplementasikan. Pisahkan dengan jelas:

- **Requirement** — apa yang dibutuhkan.
- **Constraint** — batasan yang berlaku.
- **Design Decision** — keputusan yang diambil beserta alasannya.
- **Implementation Detail** — bagaimana keputusan direalisasikan.
- **Assumption** — hal yang dianggap benar tanpa bukti penuh.
- **Open Question** — hal yang belum memiliki jawaban.

Keputusan final tidak boleh dicampur dengan hipotesis.

## 11. Architecture Documentation

Architecture documentation menjelaskan sistem pada tingkat yang sesuai. Jika relevan, dokumentasikan:

- Components
- Responsibilities
- Interfaces
- Data Flow
- Dependencies
- External Services
- Trust Boundaries
- Failure Boundaries
- Deployment Context
- Important Constraints

Architecture documentation harus mencerminkan sistem aktual. Jika implementasi berubah secara signifikan, architecture documentation harus ditinjau — konsisten dengan Architecture Standard pada ENGINEERING_STANDARD.md bagian 4.

## 12. Decision Records

Keputusan penting harus dapat dilacak. Gunakan Decision Record ketika keputusan:

1. Memiliki dampak arsitektur.
2. Memiliki dampak keamanan.
3. Mengubah product direction.
4. Memiliki trade-off penting.
5. Sulit dibalik.
6. Memengaruhi banyak sistem.

Decision Record minimal menjelaskan:

- **Context** — situasi saat keputusan dibuat.
- **Problem** — masalah yang harus diselesaikan.
- **Options Considered** — alternatif yang dievaluasi.
- **Decision** — apa yang diputuskan.
- **Reasoning** — mengapa keputusan itu diambil.
- **Consequences** — dampak yang diterima, termasuk yang tidak diinginkan.
- **Status** — proposed, accepted, superseded, atau rejected.

Jangan menghapus alasan historis hanya karena keputusan sudah lama — alasan lama menjelaskan mengapa sistem berbentuk sekarang.

## 13. Assumptions

Asumsi dipisahkan dari fakta. Gunakan kategori:

- **Confirmed** — telah diverifikasi.
- **Assumption** — dianggap benar, belum diverifikasi.
- **Unverified** — klaim yang belum diperiksa.
- **Unknown** — belum diketahui sama sekali.
- **Deprecated** — pernah dianggap benar, kini tidak lagi.

Asumsi yang menjadi dasar keputusan penting harus diverifikasi jika memungkinkan.

## 14. Open Questions

Pertanyaan yang belum terselesaikan harus dicatat, minimal mencakup:

- **Question** — pertanyaannya.
- **Context** — mengapa pertanyaan ini penting.
- **Impact** — apa yang terpengaruh selama belum dijawab.
- **Owner** — siapa yang seharusnya menjawab, jika diketahui.
- **Status** — open, being investigated, atau resolved.

Jangan mengubah open question menjadi fakta hanya untuk membuat dokumentasi terlihat lengkap.

## 15. Documentation and Code Consistency

Dokumentasi harus konsisten dengan implementasi aktual. Jika dokumentasi mengatakan sebuah fitur tersedia tetapi implementasi tidak mendukungnya, dokumentasi diperbaiki atau implementasi diperbarui melalui proses yang benar.

Dokumentasi tidak boleh digunakan untuk menyembunyikan bug. Dokumentasi juga tidak boleh digunakan untuk mendefinisikan behavior yang belum benar-benar diputuskan.

## 16. Documentation Drift

Documentation Drift terjadi ketika dokumentasi tidak lagi merepresentasikan kondisi sistem, requirement, architecture, atau keputusan yang sebenarnya. Contoh:

- Kode berubah tetapi dokumentasi tidak diperbarui.
- API berubah tetapi contract documentation tetap lama.
- Feature dihapus tetapi README masih menyebutkannya.
- Architecture berubah tetapi diagram lama tetap dianggap benar.

Perubahan signifikan harus memicu pemeriksaan dokumentasi terkait — konsisten dengan Documentation standard pada ENGINEERING_STANDARD.md bagian 15.

## 17. Documentation Lifecycle

```
Create → Review → Approve → Active → Update → Deprecate → Archive
```

1. **Create** — dokumen ditulis dengan struktur dan metadata yang sesuai.
2. **Review** — isi dokumen diperiksa oleh pihak yang relevan.
3. **Approve** — dokumen disetujui sesuai authority-nya.
4. **Active** — dokumen menjadi referensi yang berlaku.
5. **Update** — dokumen diperbarui ketika realitas berubah.
6. **Deprecate** — dokumen ditandai tidak lagi direkomendasikan.
7. **Archive** — dokumen disimpan untuk konteks historis.

Tidak semua dokumen membutuhkan proses yang sama; proses proporsional terhadap authority dan risk.

## 18. Documentation Changes

Perubahan dokumentasi mengikuti prinsip:

1. Perubahan dapat ditelusuri — melalui Git atau sistem yang setara.
2. Perubahan penting memiliki alasan yang dapat ditemukan.
3. Perubahan tidak boleh bertentangan dengan higher authority.
4. Perubahan harus diverifikasi — isi baru dicek, bukan sekadar disimpan.
5. Perubahan yang memengaruhi implementasi dikaitkan dengan perubahan sistem jika relevan.

Jangan melakukan perubahan besar secara diam-diam.

## 19. Versioning

Dokumentasi yang membutuhkan versioning membedakan perubahan:

- **Minor** — perubahan isi yang tidak mengubah makna.
- **Major** — perubahan yang mengubah makna, aturan, atau keputusan.
- **Editorial** — perbaikan typo, format, dan kejelasan tanpa perubahan substansi.

Tidak semua file wajib menggunakan semantic versioning. Jika repository menggunakan sistem versioning lain, dokumentasi mengikuti aturan repository tersebut.

## 20. Changelog

Changelog mencatat perubahan yang relevan. Bedakan:

- **Documentation Change**
- **Product Change**
- **Technical Change**
- **Security Change**
- **Breaking Change**

Jangan memasukkan setiap perubahan typo kecil jika tidak memberikan nilai.

## 21. Cross-Reference

Dokumen menggunakan referensi ke dokumen lain jika informasi saling berkaitan. Contoh:

- Product requirements → PRODUCT_STANDARD.md
- Engineering implementation → ENGINEERING_STANDARD.md
- Security requirement → SECURITY_STANDARD.md
- Company principle → NAZE_CORE.md

Hindari duplicate definitions — referensi lebih baik daripada salinan yang berpotensi melenceng.

## 22. Documentation Quality

Dokumentasi diperiksa terhadap:

- **Accuracy** — benar.
- **Clarity** — jelas.
- **Completeness** — memuat yang diperlukan untuk tujuannya.
- **Consistency** — tidak bertentangan dengan dokumen lain.
- **Traceability** — dapat ditelusuri asal dan perubahannya.
- **Freshness** — mutakhir.
- **Discoverability** — dapat ditemukan.
- **Verifiability** — klaim dapat diperiksa.

Completeness bersifat kontekstual: dokumen tidak harus menjelaskan semuanya, tetapi harus menjelaskan hal yang diperlukan untuk tujuan dokumen tersebut.

## 23. Documentation Validation

Dokumentasi penting harus dapat divalidasi. Validasi dapat mencakup:

- Link Check
- Reference Check
- Metadata Check
- Terminology Check
- Code/Documentation Consistency
- Architecture Consistency
- Requirement Traceability
- Security Consistency
- Formatting Check
- Encoding Check

Jangan menyatakan dokumentasi sudah diverifikasi jika belum ada evidence.

## 24. Documentation for AI-Assisted Development

AI dapat digunakan untuk:

- Drafting
- Summarization
- Documentation Generation
- Consistency Checking
- Terminology Checking
- Change Detection
- Technical Writing

Namun AI tidak boleh dianggap sebagai sumber kebenaran. AI tidak boleh:

1. Mengarang requirement.
2. Mengarang architecture.
3. Mengarang keputusan.
4. Mengarang testing evidence.
5. Mengklaim verifikasi yang belum dilakukan.
6. Mengubah fakta sistem tanpa evidence.

Human review tetap diperlukan untuk dokumentasi yang memiliki authority penting — konsisten dengan AI Development Policy pada NAZE_CORE.md bagian 8.

## 25. Documentation Security

Dokumentasi tidak boleh membocorkan:

- Secrets
- API Keys
- Passwords
- Private Credentials
- Sensitive Tokens
- Unnecessary Personal Data
- Internal Security Details yang tidak perlu dipublikasikan

Dokumentasi mengikuti `standards/SECURITY_STANDARD.md`, khususnya secrets management (bagian 4) dan asset classification (bagian 3). Jika dokumentasi publik dan internal memiliki kebutuhan berbeda, gunakan pemisahan informasi yang sesuai.

## 26. Public vs Internal Documentation

- **Public Documentation** — untuk pengguna eksternal; hanya memuat informasi yang aman untuk dipublikasikan.
- **Internal Documentation** — untuk tim Naze; dapat memiliki konteks teknis tambahan sesuai kebutuhan.
- **Restricted Documentation** — hanya untuk pihak berwenang; mengikuti access control yang sesuai.

## 27. Documentation Ownership

Dokumentasi penting memiliki ownership yang jelas bila diperlukan, mencakup:

- **Creation** — siapa menulis.
- **Review** — siapa memeriksa.
- **Maintenance** — siapa menjaga mutakhir.
- **Approval** — siapa menyetujui perubahan penting.
- **Retirement** — siapa memutuskan deprecation dan archive.

Ownership dokumentasi tidak otomatis berarti legal ownership terhadap produk atau perusahaan.

## 28. Documentation Discoverability

Dokumen penting harus mudah ditemukan. Gunakan:

- Clear File Names
- Predictable Directory Structure
- README References
- Cross References
- Index Documents jika diperlukan

Jangan membuat struktur dokumentasi terlalu kompleks tanpa alasan.

## 29. Documentation Anti-Patterns

- **Documentation Theater** — dokumentasi dibuat untuk terlihat ada proses, bukan untuk dibaca dan dipercaya.
- **Documentation Drift** — dokumentasi berhenti mencerminkan realitas sistem (bagian 16).
- **Duplicate Source of Truth** — dua dokumen mendefinisikan fakta yang sama dan saling bertentangan tanpa diketahui.
- **Dead Documentation** — dokumen yang tidak pernah dibaca atau dirawat, tetapi tetap dianggap berlaku.
- **Fake Completeness** — bagian diisi dengan karangan atau placeholder agar dokumen terlihat lengkap.
- **Unverified Claims** — dokumentasi menyatakan sesuatu benar tanpa evidence atau verifikasi.
- **Undocumented Decisions** — keputusan penting dibuat tanpa catatan, sehingga alasan sistem hilang.
- **Hidden Assumptions** — asumsi tertanam dalam dokumen seolah-olah fakta.
- **Overdocumentation** — dokumentasi melebihi kebutuhan, mahal dirawat, dan cepat usang.
- **Underdocumentation** — informasi penting tidak tercatat, sehingga pengetahuan hanya hidup di kepala orang.
- **Stale Examples** — contoh kode atau prosedur yang tidak lagi berfungsi.
- **Broken References** — tautan dan referensi yang menunjuk ke dokumen yang tidak ada atau sudah berubah.

## 30. Documentation Quality Gates

Quality gates dokumentasi yang proporsional:

1. **Creation Gate** — struktur, metadata, dan scope dokumen sesuai sebelum ditulis lebih jauh.
2. **Review Gate** — isi diperiksa untuk akurasi dan konsistensi sebelum diaktifkan.
3. **Activation Gate** — dokumen disetujui dan berstatus Active sesuai authority-nya.
4. **Change Gate** — perubahan penting ditinjau dan terdokumentasi.
5. **Deprecation Gate** — keputusan menandai dokumen sebagai Deprecated disertai alasan dan penggantinya.
6. **Archive Gate** — dokumen diarsipkan dengan konteks yang tetap dapat ditelusuri.

Dokumen authority tinggi membutuhkan review yang lebih ketat daripada dokumentasi implementation detail.

## 31. Relationship With Other Standards

Dokumen ini adalah **Level 2** dan berada di bawah `core/NAZE_CORE.md`.

Dokumen ini digunakan bersama:

- `standards/ENGINEERING_STANDARD.md`
- `standards/SECURITY_STANDARD.md`
- `standards/PRODUCT_STANDARD.md`

Dokumen ini tidak menduplikasi seluruh aturan dari dokumen tersebut. Jika suatu aturan sudah menjadi tanggung jawab dokumen lain, gunakan reference daripada membuat aturan berbeda.

## 32. Scope Control

Dokumen ini adalah documentation standard umum. Tidak termuat di sini: format dokumentasi spesifik per produk, tooling dokumentasi wajib, aturan gaya bahasa global, atau klaim legal. Hal-hal tersebut ditentukan pada dokumentasi produk atau repository masing-masing ketika diperlukan.

## 33. Maintenance of This Standard

Perubahan pada dokumen ini mengikuti change management NAZE_CORE.md bagian 13, dengan klasifikasi dampak mengikuti ENGINEERING_STANDARD.md bagian 13. Dokumen ini ditinjau ketika: hierarki dokumentasi berubah, anti-pattern baru teridentifikasi berulang, atau kebutuhan produk menuntut jenis dokumentasi atau proses baru.

---

**End of DOCUMENTATION_STANDARD.md**
