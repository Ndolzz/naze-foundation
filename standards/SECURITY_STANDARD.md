# NAZE SECURITY STANDARD

**Document:** SECURITY_STANDARD.md
**Type:** Security Standard
**Status:** Active
**Authority:** Level 2
**Parent Document:** NAZE_CORE.md

---

## 1. Security Philosophy

Prinsip keamanan yang berlaku pada seluruh produk Naze:

1. **Secure by Design** — keamanan dipertimbangkan sejak perancangan, bukan ditambahkan setelah sistem berjalan.
2. **Least Privilege** — setiap pengguna, komponen, dan proses hanya memiliki akses minimum yang dibutuhkan.
3. **Defense in Depth** — keamanan tidak bergantung pada satu lapisan kontrol; kegagalan satu lapisan tidak boleh langsung menjadi kompromi total.
4. **Secure Defaults** — konfigurasi bawaan harus aman; pengguna harus secara eksplisit melemahkan keamanan, bukan menyetelnya sendiri.
5. **Fail Securely** — ketika sistem gagal, sistem menolak akses atau menutup sesi, bukan membukanya.
6. **Minimize Attack Surface** — setiap endpoint, layanan, permission, dan integrasi yang tidak diperlukan dikurangi atau dihapus.
7. **Data Minimization** — hanya mengumpulkan dan menyimpan data yang benar-benar dibutuhkan.
8. **Explicit Trust Boundaries** — batas kepercayaan didefinisikan secara eksplisit; data dan permintaan yang melintasi batas diperlakukan sesuai tingkat kepercayaan sisi asalnya.
9. **Continuous Verification** — klaim keamanan diverifikasi berulang, bukan dianggap benar selamanya karena pernah diverifikasi.

## 2. Threat Modeling

Setiap produk dengan risiko keamanan signifikan harus mempertimbangkan threat modeling. Identifikasi minimal:

- **Assets** — apa yang harus dilindungi.
- **Threat Actors** — siapa yang mungkin menyerang dan motivasinya.
- **Attack Surface** — di mana sistem dapat dijangkau.
- **Trust Boundaries** — di mana data dan permintaan melintasi batas kepercayaan.
- **Potential Threats** — cara sistem dapat diserang.
- **Impact** — kerugian jika ancaman terjadi.
- **Likelihood** — kemungkinan ancaman terjadi.
- **Mitigations** — kontrol yang mengurangi risiko.
- **Residual Risk** — risiko yang tersisa setelah mitigasi.

Threat modeling yang dibuat tidak membuat sistem otomatis aman; sistem aman karena kontrolnya diterapkan dan diverifikasi.

## 3. Asset Classification

Kategori aset yang digunakan untuk menentukan tingkat perlindungan:

- **Public** — boleh diketahui umum tanpa kerugian.
- **Internal** — hanya untuk penggunaan internal; bocor berisiko rendah namun tetap tidak boleh dibocorkan.
- **Confidential** — bocor menimbulkan kerugian nyata bagi Naze atau mitra.
- **Sensitive** — data yang jika bocor membahayakan individu atau pihak tertentu (mis. data pribadi).
- **Critical** — aset yang jika rusak, hilang, atau dicuri mengganggu operasi inti atau menyebabkan kerugian besar.

Klasifikasi diterapkan berdasarkan risiko dan konteks produk, bukan berdasarkan label tetap.

## 4. Secrets Management

Secret tidak boleh disimpan di:

- Source Code
- Git Repository
- Public Documentation
- Client Bundle
- Logs
- Screenshots
- Issue Reports

Contoh secret:

- API Keys
- Access Tokens
- Passwords
- Private Keys
- Database Credentials
- Service Credentials
- Signing Keys

Jika secret terungkap:

1. Anggap secret telah compromised.
2. Revoke atau rotate secret.
3. Investigasi penggunaan secret tersebut.
4. Hapus exposure dari source bila diperlukan.
5. Dokumentasikan incident.

Prosedur spesifik per provider/produk tidak termuat di dokumen ini dan ditentukan pada dokumentasi produk masing-masing.

## 5. Authentication

Jika produk menggunakan authentication, standar minimal:

1. Authentication harus menggunakan mekanisme yang sesuai dengan risiko yang dilindunginya.
2. Credential harus dilindungi — saat disimpan, dikirim, dan diverifikasi.
3. Session harus dikelola dengan aman: pembuatan, masa berlaku, dan pengakhiran.
4. Authentication failure tidak boleh membocorkan informasi sensitif (mis. memberi tahu bagian mana dari credential yang salah).
5. Recovery mechanism harus memiliki security control setara dengan jalur authentication utamanya.
6. Authentication state harus dapat diverifikasi.

Tidak ada satu authentication provider yang ditetapkan sebagai standar global Naze.

## 6. Authorization

Authentication dan authorization dipisahkan secara konseptual:

- Authentication menjawab: **Who are you?**
- Authorization menjawab: **What are you allowed to do?**

Prinsip authorization:

1. **Least Privilege** — permission minimum yang dibutuhkan.
2. **Deny by Default** — akses ditolak kecuali secara eksplisit diizinkan.
3. **Explicit Permission** — izin dinyatakan jelas, bukan diimplikasikan.
4. **Server-Side Enforcement** — keputusan authorization diambil dan ditegakkan di sisi yang dipercaya.

Authorization tidak boleh hanya bergantung pada UI — menyembunyikan tombol bukan menolak akses.

## 7. User Data Protection

Data pengguna dikumpulkan dan diproses sesuai kebutuhan produk:

1. **Data minimization** — hanya data yang diperlukan.
2. **Purpose limitation** — data digunakan sesuai tujuan pengumpulannya.
3. **Access control** — hanya pihak berwenang yang dapat mengakses.
4. **Secure storage** — perlindungan sesuai klasifikasi aset.
5. **Secure transmission** — perlindungan saat data bergerak.
6. **Controlled retention** — data disimpan selama diperlukan, tidak selamanya tanpa keputusan.
7. **Secure deletion** — ketika diperlukan, penghapusan dilakukan secara aman dan terverifikasi.

Jangan mengumpulkan data hanya karena data tersebut tersedia.

## 8. Data in Transit

Data sensitif harus dilindungi ketika dikirim melalui jaringan, menggunakan secure transport yang sesuai dengan environment. Credential atau sensitive data tidak dimasukkan ke URL jika tidak diperlukan — URL dapat tercatat di banyak tempat yang tidak terkendali (log, history, referer).

## 9. Data at Rest

Data sensitif harus memiliki perlindungan sesuai tingkat risikonya. Pertimbangkan:

- **Encryption** — sesuai klasifikasi dan ancaman.
- **Access Control** — siapa yang dapat membaca.
- **Key Management** — bagaimana kunci dilindungi dan dirotasi.
- **Backup Protection** — backup tidak boleh menjadi titik terlemah.
- **Retention** — berapa lama data disimpan.
- **Deletion** — bagaimana data dihapus secara aman.

Detail implementasi ditentukan pada architecture masing-masing produk.

## 10. Input Validation

Semua input dari sumber yang tidak sepenuhnya dipercaya dianggap **untrusted**. Contoh sumber:

- User Input
- HTTP Request
- Uploaded File
- API Response
- External Data
- URL
- Headers
- Query Parameters
- Form Data

Input divalidasi sebelum diproses. Validasi mempertimbangkan:

- **Type**
- **Format**
- **Length**
- **Range**
- **Allowed Values**
- **Encoding**
- **Context**

## 11. Output Handling

Output diperlakukan sesuai context-nya. Risiko yang dipertimbangkan:

- **XSS** — data tidak aman dirender sebagai code di browser.
- **Injection** — data tidak aman diteruskan ke sistem lain tanpa penanganan.
- **Command Injection** — data tidak aman masuk ke command shell.
- **SQL Injection** — data tidak aman masuk ke query database.
- **Path Traversal** — data tidak aman dipakai membangun path file.
- **Template Injection** — data tidak aman masuk ke template engine.

Data tidak boleh dipercaya hanya karena berasal dari database atau API internal — data tersebut berasal dari input yang mungkin sudah tercemar.

## 12. File Upload Security

Jika produk mendukung upload file:

1. Validasi ukuran.
2. Validasi tipe.
3. Jangan mempercayai filename dari pengguna.
4. Jangan mempercayai MIME type saja.
5. Pisahkan uploaded content dari executable content.
6. Batasi storage access.
7. Pertimbangkan malware scanning sesuai risiko.
8. Jangan mengizinkan file menjadi executable secara tidak sengaja.

## 13. API Security

API harus memiliki:

- **Authentication**
- **Authorization**
- **Input Validation**
- **Rate Limiting**
- **Error Handling**
- **Logging**
- **Abuse Protection**

API response tidak boleh membocorkan:

- Secrets
- Internal Credentials
- Sensitive Debug Information
- Unnecessary Internal Architecture
- Private User Data

## 14. Rate Limiting & Abuse Prevention

Produk yang menyediakan endpoint atau resource yang dapat disalahgunakan harus mempertimbangkan rate limiting. Rate limit disesuaikan dengan:

- **Endpoint** — resource yang dilindungi.
- **User** — batas per identitas.
- **IP** — batas per sumber jaringan.
- **Authentication State** — anonymous vs authenticated.
- **Resource Cost** — operasi mahal dibatasi lebih ketat.
- **Risk** — endpoint berisiko tinggi dilindungi lebih.

Rate limiting bukan satu-satunya security control; ia adalah salah satu lapisan.

## 15. Logging & Monitoring

Security-relevant events harus dapat dideteksi jika diperlukan. Contoh:

- Authentication Failure
- Authorization Failure
- Suspicious Requests
- Privilege Changes
- Secret Exposure
- Administrative Actions
- Security Configuration Changes

Log tidak boleh berisi secret atau sensitive information yang tidak diperlukan.

## 16. Dependency Security

Dependency diperiksa secara berkala. Pertimbangkan:

- **Known Vulnerabilities** — CVE atau laporan kelemahan yang dipublikasikan.
- **Maintenance Status** — apakah dependency masih dirawat.
- **Version** — versi yang digunakan diketahui dan terkunci.
- **Origin** — dari mana dependency berasal.
- **Integrity** — keaslian paket yang diunduh.
- **Permissions** — akses apa yang diminta dependency.

Dependency yang tidak diperlukan dihapus. Jangan menambahkan dependency hanya untuk kenyamanan jika risiko atau kompleksitasnya tidak sepadan.

## 17. Third-Party Services

Third-party service dianggap sebagai external trust boundary. Sebelum digunakan, pertimbangkan:

1. Data yang dikirim ke layanan tersebut.
2. Credential yang diperlukan.
3. Permission yang diminta layanan.
4. Availability dan failure behavior-nya.
5. Implikasi privacy.
6. Ketergantungan pada vendor.
7. Exit strategy jika diperlukan.

Jangan memberikan third-party service akses lebih besar dari yang diperlukan.

## 18. AI Security

AI yang digunakan dalam produk Naze adalah komponen dengan risiko tersendiri. Pertimbangkan:

- **Prompt Injection** — instruksi berbahaya yang disisipkan melalui input pengguna atau data eksternal.
- **Indirect Prompt Injection** — instruksi berbahaya yang datang melalui data yang diambil AI (dokumen, halaman web, hasil API).
- **Data Leakage** — data sensitif yang bocor melalui prompt, log, atau output.
- **Sensitive Context Exposure** — informasi kontekstual yang tidak seharusnya dikirim ke sistem AI.
- **Unauthorized Tool Use** — agent AI menjalankan aksi di luar maksudnya.
- **Untrusted Model Output** — output model digunakan tanpa validasi.
- **Excessive Permissions** — agent AI memiliki akses lebih luas dari tugasnya.
- **Model Hallucination** — output yang terlihat benar tetapi keliru, yang jika dipakai untuk keputusan atau aksi menimbulkan risiko.

Output AI tidak boleh dianggap trusted secara otomatis. AI agent yang memiliki tool access wajib menggunakan least privilege.

## 19. Client-Side Security

Client application bukan trusted environment. Informasi yang dikirim ke client dapat dianggap dapat dilihat atau dimodifikasi oleh pengguna.

Security control penting diterapkan pada server atau trusted backend ketika diperlukan.

Secret server-side tidak boleh disimpan di:

- Mobile App
- Browser
- Frontend Bundle
- Public JavaScript
- Client Configuration

## 20. Database Security

Database mengikuti:

- **Least Privilege** — akun aplikasi tidak memiliki hak administratif.
- **Authentication** — akses ke database terautentikasi.
- **Authorization** — hanya operasi yang diperlukan yang diizinkan.
- **Input Validation** — query dibangun dengan aman.
- **Access Control** — pembatasan jaringan dan akun.
- **Backup** — data penting memiliki cadangan.
- **Auditability** — perubahan penting dapat ditelusuri.

Jika database memiliki row-level atau record-level authorization, policy tersebut wajib diuji dan diverifikasi. Database tidak otomatis "private" hanya karena tidak memiliki UI publik.

## 21. Backup & Recovery

Produk dengan data penting harus memiliki strategi:

- **Backup** — salinan data dibuat secara rutin.
- **Recovery** — prosedur pemulihan terdefinisi.
- **Restore Testing** — pemulihan dibuktikan bekerja, bukan diasumsikan.
- **Retention** — berapa lama backup disimpan.
- **Access Control** — siapa yang dapat mengakses backup.
- **Backup Protection** — backup dienkripsi dan dilindungi setara data utamanya.

Backup yang belum pernah diuji restore-nya tidak boleh dianggap sebagai recovery yang terverifikasi.

## 22. Security Testing

Security testing dipilih berdasarkan risk. Dapat mencakup:

- Dependency Scanning
- Static Analysis
- Dynamic Testing
- Authentication Testing
- Authorization Testing
- Input Validation Testing
- API Testing
- Configuration Review
- Threat Model Review

Tidak semua proyek memerlukan seluruh metode; pemilihan didasarkan pada risk dan complexity, konsisten dengan ENGINEERING_STANDARD.md bagian 9.

## 23. Vulnerability Management

Kerentanan harus:

1. Dicatat.
2. Dinilai berdasarkan risiko.
3. Diprioritaskan.
4. Diperbaiki atau dimitigasi.
5. Diverifikasi setelah perbaikan.

Severity tidak dinilai hanya berdasarkan kemudahan reproduksi bug. Pertimbangkan:

- **Impact** — apa yang rusak jika dieksploitasi.
- **Likelihood** — seberapa mungkin dieksploitasi.
- **Exposure** — apakah kerentanan dapat dijangkau pihak luar.
- **Exploitability** — usaha dan prasyarat untuk mengeksploitasi.
- **Affected Assets** — klasifikasi aset yang terdampak.

## 24. Security Incident Response

Jika terjadi security incident, alur minimal:

```
Detect
    |
    v
Contain
    |
    v
Investigate
    |
    v
Eradicate
    |
    v
Recover
    |
    v
Verify
    |
    v
Document
```

Incident response harus menjaga evidence yang relevan dan membatasi kerusakan lebih lanjut. Jika credential terkompromi, lakukan revocation atau rotation sesuai kebutuhan.

## 25. Secure Development Lifecycle

Security terintegrasi dengan engineering lifecycle:

```
Requirement
    |
    v
Threat Modeling
    |
    v
Architecture
    |
    v
Implementation
    |
    v
Security Testing
    |
    v
Verification
    |
    v
Release
    |
    v
Monitoring
```

Security bukan hanya tahap terakhir sebelum release — ia hadir dari requirement sampai monitoring.

## 26. Security Definition of Done

Untuk perubahan yang memiliki security impact, minimal periksa:

- Threats considered
- Permissions reviewed
- Input validated
- Secrets protected
- Authorization verified
- Security tests completed
- Sensitive logging reviewed
- Documentation updated

Tingkat pemeriksaan proporsional terhadap risk, konsisten dengan Definition of Done pada ENGINEERING_STANDARD.md.

## 27. Security Anti-Patterns

- **Hardcoded Secrets** — secret di dalam kode; siapa pun yang membaca kode atau riwayat Git memperoleh akses.
- **Client-Side Trust** — memperlakukan client sebagai terpercaya; kontrol penting dilewati dengan request langsung.
- **Broken Authorization** — authentication benar tetapi authorization longgar; pengguna sah dapat mengakses data orang lain.
- **Overprivileged Access** — akun, komponen, atau agent memiliki izin jauh melampaui kebutuhannya, memperluas dampak kompromi.
- **Unvalidated Input** — input diproses tanpa validasi, membuka jalur injection dan data corruption.
- **Sensitive Data in Logs** — log menyimpan credential atau data pribadi, mengubah alat diagnostik menjadi sumber kebocoran.
- **Security Through Obscurity** — bergantung pada kerahasiaan implementasi, bukan pada kontrol yang tetap bekerja meski rahasia itu bocor.
- **Unverified AI Output** — output AI dipakai atau dieksekusi tanpa validasi, termasuk risiko prompt injection dan hallucination yang diperlakukan sebagai fakta.
- **Unpatched Dependencies** — dependency dengan kerentanan diketahui tetap digunakan tanpa mitigasi.
- **Untested Backups** — backup ada tetapi restore-nya tidak pernah dibuktikan; kegagalan nyata terjadi justru saat dipulihkan.

## 28. Security Exceptions

Jika suatu standar keamanan tidak dapat diterapkan:

1. Exception didokumentasikan.
2. Alasan dinyatakan jelas.
3. Risiko diidentifikasi.
4. Mitigasi ditentukan jika memungkinkan.
5. Exception memiliki review dan expiry/reassessment jika relevan.

Exception bukan cara untuk menghapus security control tanpa alasan — exception yang tidak ditinjau kembali adalah security debt yang tersembunyi.

## 29. Compliance & Legal Scope

Dokumen ini tidak membuat klaim bahwa Naze memenuhi standar hukum, regulasi, sertifikasi, atau compliance tertentu. Kebutuhan compliance ditentukan berdasarkan:

- Product
- Jurisdiction
- Data Type
- Users
- Business Model
- Applicable Regulation

Jika compliance diperlukan, requirement tersebut didokumentasikan secara eksplisit pada dokumen produk yang relevan.

## 30. Relationship With Other Standards

Dokumen ini adalah **Level 2** dan tunduk kepada **Level 1: NAZE_CORE.md**. Saat konflik, NAZE_CORE.md memiliki authority lebih tinggi.

Security Standard digunakan bersama:

- ENGINEERING_STANDARD.md
- PRODUCT_STANDARD.md (ketika telah dibuat)

Security requirement yang spesifik terhadap suatu produk berada pada dokumentasi produk tersebut.

## 31. Maintenance of This Standard

Perubahan pada dokumen ini mengikuti change management NAZE_CORE.md bagian 13, dengan klasifikasi dampak mengikuti Security-Sensitive Change pada ENGINEERING_STANDARD.md bagian 13. Dokumen ini ditinjau ketika: threat baru teridentifikasi berulang, incident mengungkap gap standar, atau produk Naze memperkenalkan kategori risiko baru.

---

**End of SECURITY_STANDARD.md**
