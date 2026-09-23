# NAZE PRODUCT STANDARD

**Document:** PRODUCT_STANDARD.md
**Type:** Product Standard
**Status:** Active
**Authority:** Level 2
**Parent Document:** NAZE_CORE.md

---

## 1. Product Philosophy

Produk Naze harus:

1. Memiliki tujuan yang jelas.
2. Menyelesaikan masalah yang nyata.
3. Memiliki scope yang terdefinisi.
4. Memiliki pengguna atau use case yang jelas.
5. Dapat diverifikasi.
6. Dapat dipelihara.
7. Memiliki alasan yang jelas untuk setiap fitur utama.

Produk tidak dinilai berdasarkan jumlah fitur — produk dinilai berdasarkan seberapa baik ia menyelesaikan masalah yang didefinisikannya dan dapat dipelihara dalam jangka panjang. Standar ini berlaku untuk semua jenis produk Naze: Web, Mobile App, Desktop App, Python Software, AI Product, Automation, Bot, API, Internal Tool, dan Digital Service.

## 2. Product Lifecycle

Lifecycle standar produk Naze:

```
Idea
    |
    v
Discovery
    |
    v
Definition
    |
    v
Specification
    |
    v
Design
    |
    v
Development
    |
    v
Validation
    |
    v
Release
    |
    v
Monitoring
    |
    v
Iteration
    |
    v
Maintenance
    |
    v
Retirement
```

1. **Idea** — gagasan produk dicatat beserta masalah yang diklaim diselesaikannya.
2. **Discovery** — masalah, pengguna, dan konteks dipahami sebelum berkomitmen membangun.
3. **Definition** — produk didefinisikan: tujuan, scope, pengguna, dan success criteria.
4. **Specification** — behavior dan acceptance criteria produk ditetapkan.
5. **Design** — produk dirancang agar sesuai tujuan dan penggunanya.
6. **Development** — produk dibangun mengikuti ENGINEERING_STANDARD.md.
7. **Validation** — produk dibuktikan memenuhi requirement dan expectation yang ditetapkan.
8. **Release** — produk disampaikan ke penggunanya dengan dokumentasi dan catatan rilis.
9. **Monitoring** — perilaku produk dipantau setelah rilis.
10. **Iteration** — perbaikan dan penyempurnaan dilakukan berdasarkan evidence.
11. **Maintenance** — produk dipelihara, termasuk bug, dependency, dan technical debt.
12. **Retirement** — produk dihentikan secara terencana ketika tidak lagi dipertahankan.

Lifecycle diterapkan secara proporsional — produk kecil tidak menuntut proses seberkat produk besar, tetapi tidak ada tahap yang boleh dilompati tanpa keputusan yang terdokumentasi.

## 3. Product Discovery

Sebelum produk besar dikembangkan, kebutuhan harus dipahami. Pertimbangkan:

- **Problem** — masalah apa yang diselesaikan, dan untuk siapa.
- **Users** — siapa penggunanya dan konteks penggunaannya.
- **Use Case** — bagaimana produk akan benar-benar digunakan.
- **Existing Alternatives** — apa yang dipakai orang hari ini untuk masalah yang sama.
- **Constraints** — batasan teknis, sumber daya, dan waktu.
- **Risks** — apa yang bisa salah, termasuk risiko membangun sesuatu yang tidak dibutuhkan.
- **Expected Value** — nilai yang diharapkan jika produk berhasil.

Sebuah masalah tidak dianggap nyata hanya karena seseorang mengatakan ia ada. Jika memungkinkan, gunakan evidence — data, observasi, atau percobaan — sebelum berkomitmen.

## 4. Product Definition

Setiap produk harus memiliki definisi yang jelas. Minimal:

- **Product Name**
- **Purpose**
- **Problem**
- **Target Users**
- **Primary Use Cases**
- **Scope**
- **Out of Scope**
- **Core Value**
- **Constraints**
- **Success Criteria**

Jika suatu informasi belum diketahui, jangan mengarang — tandai sebagai keputusan yang belum dibuat, sesuai Decision Framework pada NAZE_CORE.md.

## 5. Scope Management

Setiap produk memiliki batas:

- **In Scope** — apa yang termasuk.
- **Out of Scope** — apa yang secara eksplisit tidak termasuk.
- **Future Consideration** — apa yang mungkin dipertimbangkan nanti, bukan sekarang.

Fitur yang tidak termasuk scope tidak boleh ditambahkan hanya karena mudah dibuat. Setiap scope change harus dapat ditelusuri: apa yang berubah, mengapa, dan apa dampaknya.

## 6. User & Use Case

Use case menjelaskan bagaimana produk digunakan. Setiap use case utama sebaiknya memiliki:

- **Actor** — siapa yang terlibat.
- **Goal** — apa yang ingin dicapai actor.
- **Precondition** — apa yang harus benar sebelum use case dijalankan.
- **Action** — langkah yang dilakukan.
- **Expected Result** — hasil yang diharapkan jika berhasil.
- **Failure Case** — apa yang terjadi dan bagaimana ditangani jika gagal.

Fitur tidak dibangun hanya berdasarkan asumsi mengenai perilaku pengguna; asumsi diuji atau diakui sebagai asumsi.

## 7. Requirements

Product requirements harus:

1. Jelas.
2. Spesifik.
3. Dapat diverifikasi.
4. Tidak ambigu.
5. Memiliki prioritas jika diperlukan.
6. Dapat ditelusuri ke acceptance criteria.

Tiga hal dibedakan dan tidak dicampur:

- **Product Requirement** — apa yang dibutuhkan dari sudut pandang produk dan pengguna.
- **Technical Requirement** — kebutuhan teknis yang timbul dari product requirement.
- **Implementation Detail** — bagaimana kebutuhan direalisasikan.

## 8. Feature Management

Setiap fitur utama memiliki:

- **Purpose**
- **User Benefit**
- **Requirement**
- **Dependencies**
- **Risks**
- **Acceptance Criteria**

Fitur dievaluasi berdasarkan:

- **User Value**
- **Complexity**
- **Risk**
- **Maintenance Cost**
- **Security Impact**

Evaluasi bersifat kualitatif atau kuantitatif sesuai konteks produk; tidak ada sistem ranking atau scoring universal yang memaksa semua produk memakai angka yang sama.

## 9. MVP & Iterative Development

Produk baru dapat dikembangkan secara bertahap. MVP harus:

1. Memiliki tujuan yang jelas — versi pertama yang paling kecil yang tetap bernilai.
2. Memiliki scope terbatas dan didefinisikan.
3. Tetap memenuhi security baseline SECURITY_STANDARD.md.
4. Tetap dapat diverifikasi.
5. Tidak menggunakan label MVP sebagai alasan mengabaikan requirement penting.

MVP bukan berarti produk boleh dibuat secara sembarangan — ia adalah versi terbatas yang dibuat secara disiplin.

## 10. Product Design

Design harus mendukung tujuan produk. Pertimbangkan:

- **Usability**
- **Accessibility**
- **Consistency**
- **Information Architecture**
- **Navigation**
- **Feedback**
- **Error States**
- **Loading States**
- **Empty States**
- **Responsive Behavior**

Design mempertimbangkan platform yang digunakan (web, mobile, desktop, CLI, atau antarmuka non-visual seperti bot dan API — yang tetap memiliki prinsip usability dan konsistensinya sendiri). Aturan visual global yang terlalu spesifik tidak ditetapkan di dokumen ini.

## 11. Accessibility

Produk mempertimbangkan accessibility sesuai platform dan target penggunanya:

- **Readable Content**
- **Keyboard / Alternative Navigation**
- **Contrast**
- **Text Scaling**
- **Input Assistance**
- **Error Feedback**
- **Semantic Structure**
- **Motion Sensitivity**

Tingkat accessibility disesuaikan dengan jenis produk dan platform; API dan automation memiliki batas aksesibilitas yang berbeda dari aplikasi visual, dan keduanya tetap wajib dipertimbangkan secara eksplisit.

## 12. Product Performance

Performance dipertimbangkan berdasarkan use case:

- **Startup Time**
- **Response Time**
- **Memory Usage**
- **CPU Usage**
- **Network Usage**
- **Battery Usage**
- **Storage Usage**
- **Scalability**

Optimization tidak dilakukan tanpa evidence bahwa optimization diperlukan — gunakan measurement jika memungkinkan, konsisten dengan larangan Unnecessary Complexity pada ENGINEERING_STANDARD.md.

## 13. Reliability

Produk harus memiliki behavior yang dapat diprediksi. Pertimbangkan:

- **Failure Modes** — bagaimana produk gagal.
- **Timeout** — perilaku saat operasi lambat atau menggantung.
- **Retry** — kapan percobaan ulang aman dan masuk akal.
- **Offline Behavior** — perilaku tanpa konektivitas, jika relevan.
- **Recovery** — bagaimana kembali normal setelah kegagalan.
- **Data Consistency** — data tetap benar melintasi kegagalan.
- **Graceful Degradation** — fungsi inti bertahan saat sebagian sistem gagal.

Failure ditangani secara eksplisit, konsisten dengan Error Handling pada ENGINEERING_STANDARD.md.

## 14. Privacy

Produk yang menangani data pengguna harus menentukan:

- **Data Collected** — data apa yang dikumpulkan.
- **Purpose** — untuk apa data digunakan.
- **Access** — siapa yang dapat mengakses.
- **Retention** — berapa lama disimpan.
- **Deletion** — bagaimana dihapus.
- **Third-Party Sharing** — apakah dan ke mana data dibagikan.

Privacy requirement konsisten dengan SECURITY_STANDARD.md bagian 7 (User Data Protection). Klaim compliance atau legal tidak dibuat sebelum diverifikasi, sesuai SECURITY_STANDARD.md bagian 29.

## 15. Product Security

Product development mengikuti `standards/SECURITY_STANDARD.md`. Security requirement dimasukkan sejak tahap product definition dan specification — bukan sebagai fitur tambahan setelah produk selesai.

## 16. Product Validation

Sebelum release, produk divalidasi terhadap:

- Requirements
- Use Cases
- Acceptance Criteria
- Security Requirements
- Performance Expectations
- Reliability Expectations
- Accessibility Expectations

Validation menghasilkan evidence yang dapat diperiksa — bukan pernyataan "sudah oke". Validation berbeda dari testing, konsisten dengan ENGINEERING_STANDARD.md bagian 10.

## 17. Acceptance Criteria

Setiap requirement atau fitur penting memiliki acceptance criteria yang dapat diuji, menjelaskan kondisi yang diperlukan agar requirement dianggap terpenuhi.

Kriteria yang terlalu subjektif dihindari:

- "Looks good"
- "Feels fast"
- "Works perfectly"
- "Very secure"
- "Professional enough"

Gunakan kondisi yang dapat diamati atau diverifikasi — mis. "respons pencarian muncul dalam waktu X pada data Y", bukan "terasa cepat".

## 18. Release Readiness

Sebelum release, periksa minimal:

- **Requirements** — terpenuhi atau penyimpangannya tercatat.
- **Testing** — test yang relevan selesai dan lulus.
- **Verification** — acceptance criteria terpenuhi.
- **Security** — security gate terpenuhi sesuai risk.
- **Documentation** — mutakhir.
- **Known Issues** — tercatat dengan status jelas.
- **Configuration** — konfigurasi release diketahui dan terkendali.
- **Release Notes** — perubahan utama terdokumentasi.
- **Rollback / Recovery Considerations** — rencana jika release bermasalah.

Tingkat pemeriksaan disesuaikan dengan risk, konsisten dengan Quality Gates pada ENGINEERING_STANDARD.md.

## 19. Versioning & Releases

Produk memiliki cara yang jelas untuk membedakan release. Release information minimal memungkinkan identifikasi:

- **Version**
- **Release Date**
- **Major Changes**
- **Known Issues**
- **Breaking Changes**

Strategi versioning spesifik ditentukan oleh masing-masing produk; tidak ada satu versioning scheme yang dipaksakan untuk semua produk.

## 20. Monitoring & Feedback

Produk yang telah dirilis dipantau sesuai kebutuhan. Pertimbangkan:

- **Errors**
- **Crashes**
- **Performance**
- **Availability**
- **Security Events**
- **User Feedback**
- **Usage Patterns**

Data monitoring dikumpulkan secara proporsional dan tidak melanggar security atau privacy requirements — konsisten dengan Logging & Monitoring pada SECURITY_STANDARD.md.

## 21. Product Metrics

Metrics digunakan untuk membantu pengambilan keputusan, dan setiap metric harus memiliki tujuan yang jelas. Contoh kategori:

- **Reliability**
- **Performance**
- **Usage**
- **Retention**
- **Conversion**
- **Support**
- **Quality**

Metric tidak dibuat hanya karena mudah diukur, dan satu metric tidak dianggap dapat menggambarkan seluruh kualitas produk.

## 22. Feedback & Change

Feedback pengguna adalah input product development, tetapi feedback tidak otomatis menjadi requirement. Alurnya:

```
Feedback
    |
    v
Analysis
    |
    v
Decision
    |
    v
Requirement
    |
    v
Specification
    |
    v
Implementation
```

Keputusan tetap mempertimbangkan scope, risk, security, dan maintenance — mengubah requirement berdasarkan feedback satu orang tanpa analisis adalah pelanggaran standar ini.

## 23. Bug Management

Bug diklasifikasikan dan ditangani berdasarkan dampak. Pertimbangkan:

- **Impact**
- **Frequency**
- **Severity**
- **Security Risk**
- **Affected Users**
- **Workaround**

Bug tidak boleh ditutupi dengan mengubah dokumentasi agar behavior yang salah terlihat seperti behavior yang direncanakan — itu adalah documentation drift dan false verification sekaligus.

## 24. Product Documentation

Setiap produk memiliki dokumentasi sesuai kompleksitasnya. Minimal pertimbangkan:

- **Overview**
- **Purpose**
- **Requirements**
- **Architecture Reference**
- **Usage**
- **Configuration**
- **Security**
- **Testing**
- **Release Notes**
- **Known Issues**

Dokumentasi harus mencerminkan keadaan sistem yang sebenarnya, konsisten dengan Documentation standard pada ENGINEERING_STANDARD.md.

## 25. Product Ownership

Setiap produk memiliki ownership yang jelas, mencakup tanggung jawab terhadap:

- **Product Direction**
- **Requirements**
- **Documentation**
- **Release**
- **Maintenance**
- **Security Coordination**
- **Technical Decisions**

Ownership tidak otomatis berarti struktur legal atau jabatan perusahaan tertentu — pada tahap ini, ownership dapat dipegang oleh Naze founder/owner sesuai Governance Authority pada NAZE_CORE.md bagian 16.

## 26. Product Dependencies

Ketergantungan antar produk harus diketahui. Contoh:

```
Product A
    |
    v
Shared Service
    |
    v
Product B
```

Dependency penting didokumentasikan. Produk tidak boleh bergantung pada komponen yang tidak diketahui status, ownership, atau lifecycle-nya.

## 27. Deprecation

Produk atau fitur yang tidak lagi dipertahankan memiliki status yang jelas:

- **Active** — dikembangkan dan dipelihara penuh.
- **Maintenance** — tanpa pengembangan baru, hanya perbaikan penting.
- **Deprecated** — tidak direkomendasikan, dengan pengganti atau jadwal penghentian.
- **Retired** — tidak lagi beroperasi.

Jika produk atau fitur akan dihentikan, pertimbangkan: **Users, Data, Dependencies, Migration, Communication, Security, Removal.** Komponen production tidak dihapus secara tiba-tiba tanpa memahami dampaknya.

## 28. Product Retirement

Jika sebuah produk dihentikan:

```
Decision
    |
    v
Impact Assessment
    |
    v
Data Strategy
    |
    v
Dependency Review
    |
    v
User Impact
    |
    v
Shutdown
    |
    v
Verification
    |
    v
Documentation
```

Setelah retirement, pastikan secret, access, infrastructure, dan dependency yang tidak lagi diperlukan ditangani — secret yang tertinggal pada produk mati tetap menjadi risiko, konsisten dengan SECURITY_STANDARD.md bagian 4.

## 29. AI-Assisted Product Development

AI dapat digunakan untuk:

- Research
- Ideation
- Requirement Drafting
- Design Exploration
- Implementation
- Testing
- Analysis
- Documentation

Namun AI tidak boleh menjadi satu-satunya dasar keputusan produk. Output AI harus diverifikasi. AI tidak boleh membuat requirement, user need, market fact, atau product evidence seolah-olah telah diverifikasi jika sebenarnya belum — konsisten dengan AI Development Policy pada NAZE_CORE.md dan AI-Assisted Development pada ENGINEERING_STANDARD.md.

## 30. Product Anti-Patterns

- **Feature Bloat** — fitur ditambah tanpa kebutuhan terverifikasi, menambah beban pemeliharaan dan kompleksitas tanpa nilai yang sepadan.
- **Building Without Problem Definition** — membangun sebelum masalah dipahami, menghasilkan produk yang rapi menyelesaikan sesuatu yang tidak dibutuhkan.
- **Scope Creep** — scope meluas diam-diam tanpa keputusan dan penelusuran, membuat estimasi dan prioritas kehilangan makna.
- **Assumption-Driven Development** — asumsi tentang pengguna dipakai sebagai fakta tanpa diuji.
- **Unverified User Need** — kebutuhan pengguna diklaim ada tanpa evidence apa pun.
- **Premature Scaling** — arsitektur dan infrastruktur dibangun untuk beban yang belum terjadi.
- **Premature Optimization** — optimasi dilakukan tanpa measurement yang menjustifikasinya.
- **Ignoring Accessibility** — sebagian pengguna dikecualikan karena accessibility dianggap tambahan opsional.
- **Ignoring Security** — security ditunda "sampai produk jadi", membuat perbaikan makin mahal dan risiko makin nyata.
- **Documentation Drift** — dokumentasi berhenti menggambarkan produk yang sebenarnya.
- **Fake Validation** — produk dinyatakan tervalidasi tanpa evidence yang dapat diperiksa.

## 31. Product Quality Gates

Quality gates produk:

1. **Discovery Gate** — masalah dan kebutuhan dipahami dengan cukup evidence untuk melanjutkan.
2. **Definition Gate** — definisi produk lengkap dan tidak mengarang informasi.
3. **Specification Gate** — specification ada, jelas, dan memiliki acceptance criteria.
4. **Development Gate** — implementasi sesuai specification dan standar engineering.
5. **Validation Gate** — evidence validation tersedia dan dapat diperiksa.
6. **Security Gate** — security requirement terpenuhi sesuai risk.
7. **Release Gate** — release readiness terpenuhi.
8. **Maintenance Gate** — produk yang dirilis tetap dipelihara dan dipantau.
9. **Retirement Gate** — penghentian dilakukan terencana dengan dampak ditangani.

Gate proporsional terhadap risk dan complexity: perubahan berisiko rendah boleh melewati gate yang disederhanakan, tetapi tidak ada gate yang diniadakan tanpa keputusan yang terdokumentasi.

## 32. Relationship With Other Standards

Dokumen ini adalah **Level 2** dan tunduk kepada **Level 1: NAZE_CORE.md**. Jika terjadi konflik dengan Level 1, Level 1 memiliki authority lebih tinggi.

Dokumen ini digunakan bersama:

- ENGINEERING_STANDARD.md
- SECURITY_STANDARD.md

Jika terjadi overlap, dokumen ini menghindari duplikasi dan mereferensikan dokumen yang memiliki tanggung jawab tersebut: engineering execution merujuk ENGINEERING_STANDARD.md; keamanan merujuk SECURITY_STANDARD.md.

## 33. Scope Control

Dokumen ini adalah product standard umum untuk semua jenis produk Naze. Tidak termuat di sini: arsitektur produk spesifik, keputusan teknologi, prioritas produk tertentu, aturan visual global, dan klaim legal/compliance. Hal-hal tersebut ditentukan pada dokumentasi produk masing-masing ketika diperlukan.

## 34. Maintenance of This Standard

Perubahan pada dokumen ini mengikuti change management NAZE_CORE.md bagian 13, dengan klasifikasi dampak mengikuti ENGINEERING_STANDARD.md bagian 13. Dokumen ini ditinjau ketika: jenis produk baru memerlukan prinsip yang belum tercakup, anti-pattern baru teridentifikasi berulang, atau lifecycle standar tidak lagi mencerminkan praktik yang sehat.

---

**End of PRODUCT_STANDARD.md**
