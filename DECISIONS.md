# Naze Foundation — Open Decisions Log

**Document:** DECISIONS.md
**Type:** Decision Tracking
**Status:** Active
**Authority:** Level 3 (tunduk kepada NAZE_CORE.md dan seluruh standar Level 2)
**Owner:** Naze founder/owner
**Related Documents:** NAZE_CORE.md, DOCUMENTATION_STANDARD.md (bagian 12–14)

---

Dokumen ini mencatat keputusan yang **belum** dibuat dan keputusan yang **sudah** dibuat. Sesuai NAZE_CORE.md bagian 15 (Decision Framework): keputusan yang belum ada tidak boleh dikarang, dan harus dicatat di dokumen — bukan hanya dalam ingatan atau percakapan.

## 1. Open Decisions

Format per entri mengikuti Open Questions pada DOCUMENTATION_STANDARD.md bagian 14.

### D-001 — Status legal Naze

- **Question:** Apakah bentuk badan hukum Naze (jika ada), dan kapan didaftarkan?
- **Context:** NAZE_CORE.md bagian 16 menyatakan status legal belum ditetapkan. Semua dokumen foundation dilarang membuat klaim legal.
- **Impact:** Kepemilikan formal, kontrak, komersialisasi, dan compliance requirement tertunda sampai keputusan ini dibuat.
- **Owner:** Naze founder/owner.
- **Status:** Open.

### D-002 — Struktur organisasi dan ownership formal

- **Question:** Bagaimana struktur organisasi dan pembagian tanggung jawab formal Naze?
- **Context:** Belum ada tim atau struktur yang ditetapkan; governance authority saat ini dipegang Naze founder/owner.
- **Impact:** Approval chain untuk perubahan Level 1 saat ini satu orang; belum ada delegasi authority.
- **Owner:** Naze founder/owner.
- **Status:** Open.

### D-003 — Produk pertama Naze

- **Question:** Produk apa yang dikembangkan pertama kali?
- **Context:** NAZE_CORE.md bagian 11 menyatakan belum ada produk individu yang ditetapkan. PRODUCT_STANDARD.md menunggu produk nyata untuk diterapkan.
- **Impact:** Seluruh standar Level 2 belum pernah diuji terhadap produk nyata; discovery gate pertama belum pernah dijalankan.
- **Owner:** Naze founder/owner.
- **Status:** Open.

### D-004 — Strategi versioning repository foundation

- **Question:** Apakah repository foundation ini memakai semantic versioning per dokumen, atau mengandalkan Git history saja?
- **Context:** DOCUMENTATION_STANDARD.md bagian 19 menyatakan versioning opsional dan mengikuti aturan repository; repo ini belum menetapkan aturannya.
- **Impact:** Metadata `Version` pada dokumen penting belum terisi secara konsisten.
- **Owner:** Naze founder/owner.
- **Status:** Open.

### D-005 — Git hosting resmi dan akses repository

- **Question:** Apakah GitHub pada akun pribadi (`Ndolzz`) menjadi lokasi resmi jangka panjang repository ini, atau dipindahkan ke organisasi tersendiri?
- **Context:** Repository saat ini berada di akun pribadi; belum ada keputusan tentang organisasi, backup, atau akses tambahan.
- **Impact:** Kelangsungan dan akses repository terikat pada satu akun.
- **Owner:** Naze founder/owner.
- **Status:** Open.

### D-006 — Kebutuhan compliance

- **Question:** Regulasi atau standar compliance mana yang relevan bagi produk Naze (jika ada)?
- **Context:** SECURITY_STANDARD.md bagian 29 melarang klaim compliance sebelum diverifikasi; kebutuhan ditentukan per produk, yurisdiksi, dan tipe data.
- **Impact:** Tidak ada sebelum ada produk dan data pengguna nyata.
- **Owner:** Menunggu keputusan D-003.
- **Status:** Open — blocked by D-003.

## 2. Decided

Format per entri mengikuti Decision Record pada DOCUMENTATION_STANDARD.md bagian 12. Keputusan berikut tercatat dari sejarah pembuatan repository.

### DR-001 — Inisialisasi foundation sebelum produk

- **Context:** Naze dimulai tanpa produk; ada kebutuhan acuan sebelum membangun.
- **Problem:** Bagaimana memastikan seluruh produk Naze masa depan berdiri di atas prinsip yang sama?
- **Options Considered:** (1) membangun produk langsung dan mendokumentasikan belakangan; (2) membangun fondasi dokumentasi terlebih dahulu.
- **Decision:** Membangun `naze-foundation` sebagai repository fondasi; produk tertunda hingga fondasi selesai direview.
- **Reasoning:** Sesuai NAZE_CORE.md — fondasi sebelum produk; mencegah standar ditulis menyusul implementasi.
- **Consequences:** Fondasi harus dirawat; produk tidak bisa dimulai sebelum review manusia selesai.
- **Status:** Accepted.

### DR-002 — Struktur standar Level 2

- **Context:** Perlu menentukan dokumen Level 2 apa yang dibuat pada fase fondasi.
- **Problem:** Dokumen mana yang benar-benar diperlukan sekarang?
- **Options Considered:** (1) membuat banyak dokumen sekaligus; (2) membuat bertahap hanya yang dibutuhkan.
- **Decision:** Empat standar Level 2: Engineering, Security, Product, Documentation — masing-masing dibuat melalui task terpisah, tanpa dokumen lain yang belum diperlukan.
- **Reasoning:** Prinsip kesederhanaan NAZE_CORE.md; setiap dokumen dibuat saat kebutuhannya nyata.
- **Consequences:** Standar Level 2 dianggap lengkap untuk fase ini; penambahan berikutnya menunggu kebutuhan nyata.
- **Status:** Accepted.

## 3. Review Status Dokumen Foundation

Sesuai DOCUMENTATION_STANDARD.md bagian 7: seluruh dokumen ditulis dengan bantuan AI dan **belum melewati human review**. Sampai direview manusia, seluruh dokumen foundation berlaku sebagai berikut:

| Dokumen | Status Efektif |
|---|---|
| core/NAZE_CORE.md | Review (menunggu approval manusia) |
| standards/ENGINEERING_STANDARD.md | Review |
| standards/SECURITY_STANDARD.md | Review |
| standards/PRODUCT_STANDARD.md | Review |
| standards/DOCUMENTATION_STANDARD.md | Review |
| README.md | Review |

Keputusan mengubah status menjadi **Active** milik Naze founder/owner (NAZE_CORE.md bagian 16, Governance Authority).

---

**End of DECISIONS.md**
