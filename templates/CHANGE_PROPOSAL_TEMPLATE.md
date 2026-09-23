# Change Proposal Template

**Template:** CHANGE_PROPOSAL_TEMPLATE.md
**Type:** Governance Form
**Status:** Active
**Authority:** Level 3
**Parent:** NAZE_CORE.md (bagian 13), ENGINEERING_STANDARD.md (bagian 13)

---

Gunakan template ini untuk mengajukan perubahan, terutama perubahan pada dokumen Level 1 atau Level 2. Salin ke tempat yang sesuai, isi, dan hapus bagian yang tidak relevan berserta catatannya.

```
Change Proposal: CP-<nomor urut>
Title: <judul singkat>
Date: <tanggal diajukan>
Proposer: <nama>
Target Document(s): <path dokumen yang diubah>
Change Classification: Minor / Major / Architecture / Breaking / Security-Sensitive

1. Reason for Change
   <mengapa perubahan ini diperlukan; masalah atau kebutuhan nyata>

2. Proposed Change
   <apa yang berubah; ringkasan, bukan diff penuh>

3. Impact Analysis
   - Dampak terhadap dokumen turunan: <daftar dokumen Level 2/3 yang terpengaruh>
   - Dampak terhadap implementasi: <jika ada sistem yang mengikuti dokumen ini>
   - Dampak keamanan: <jika ada>

4. Alternatives Considered
   <opsi lain yang dievaluasi dan mengapa ditolak>

5. Review
   Reviewer: <nama>
   Catatan review: <temuan atau persetujuan bersyarat>

6. Approval
   Approved by: <pihak dengan kewenangan atas Naze — Naze founder/owner untuk Level 1>
   Date: <tanggal>

7. Git Commit
   Commit/PR: <referensi commit atau pull request>
```

Catatan:
- Perubahan Level 1 (NAZE_CORE.md) wajib melalui seluruh tahap dan disetujui Naze founder/owner.
- Perubahan tanpa approval tidak boleh dipush untuk dokumen Level 1 dan Level 2.
- Proposal yang ditolak tetap dicatat beserta alasannya.

---

**End of CHANGE_PROPOSAL_TEMPLATE.md**
