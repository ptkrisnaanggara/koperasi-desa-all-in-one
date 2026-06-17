# PRD — Sistem Koperasi All-in-One (KDMP)

**Product Requirements Document**
Sistem Informasi Koperasi Terpadu untuk Program Koperasi Desa/Kelurahan Merah Putih (KDMP)

| | |
|---|---|
| **Nama Produk** | Koperasi Desa All-in-One |
| **Versi Dokumen** | 1.0 |
| **Tanggal** | 17 Juni 2026 |
| **Status** | Draft |
| **Pemilik Produk** | _(diisi)_ |
| **Cakupan Jenis Koperasi** | Simpan Pinjam, Serba Usaha, Konsumen, Produsen, Jasa |
| **Program Acuan** | Koperasi Desa/Kelurahan Merah Putih (KDMP) — Inpres No. 9 Tahun 2025 |

---

## 1. Ringkasan Eksekutif

**Koperasi Desa All-in-One** adalah platform digital terpadu (web + mobile) yang dirancang untuk mengelola seluruh operasional koperasi multi-unit usaha sesuai amanat program **Koperasi Desa/Kelurahan Merah Putih (KDMP)**. Sistem ini menyatukan lima jenis koperasi dalam satu basis data dan satu badan hukum koperasi: **Simpan Pinjam, Serba Usaha, Konsumen, Produsen, dan Jasa**.

Tujuan utama produk adalah memberikan koperasi desa kemampuan untuk:
- Mengelola keanggotaan, simpanan, dan pinjaman secara akuntabel dan transparan.
- Menjalankan unit-unit usaha (gerai sembako, apotek, klinik, logistik, cold storage) dalam satu sistem kasir dan inventori.
- Menghasilkan laporan keuangan dan laporan SHU (Sisa Hasil Usaha) otomatis.
- Memenuhi kewajiban pelaporan kepada Kementerian Koperasi, Dinas Koperasi, serta bank penyalur (Himbara) terkait pengembalian pinjaman modal.

### 1.1 Konteks Program KDMP

Program KDMP diluncurkan secara nasional pada **21 Juli 2025** berdasarkan **Instruksi Presiden (Inpres) No. 9 Tahun 2025** tentang percepatan pembentukan Koperasi Merah Putih. Program ini menargetkan pembentukan puluhan ribu koperasi tingkat desa/kelurahan yang berperan sebagai **simpul rantai pasok desa** untuk kebutuhan pokok, hasil pertanian, dan obat-obatan.

Skema pembiayaan tiap koperasi berada pada kisaran **Rp 3–5 miliar per desa**, bersumber dari kombinasi dana desa dan pinjaman bank Himbara, dengan tenor pengembalian **3–5 tahun**. Karena modal program ini berasal dari pinjaman yang harus dikembalikan, **akuntabilitas keuangan dan kelayakan usaha (viability) menjadi kebutuhan kritis** — dan inilah alasan utama keberadaan sistem digital ini.

> Sumber konteks program: [ARMA Law — Inpres 9/2025](https://arma-draft.squarespace.com/news-event/newsflash/koperasi-merah-putih-a-national-strategy-for-inclusive-growth), [Kompas — skema pembiayaan](https://www.kompas.id/artikel/en-kado-pahit-itu-bernama-koperasi-desa-merah-putih), [Tempo — peluncuran nasional](https://en.tempo.co/read/2030823/prabowo-launches-over-80000-red-and-white-cooperatives-108-already-operational). _Konten telah diparafrasekan untuk kepatuhan lisensi._

---

## 2. Latar Belakang & Permasalahan

### 2.1 Permasalahan yang Diselesaikan

| # | Permasalahan | Dampak Tanpa Sistem |
|---|---|---|
| P1 | Pencatatan manual (buku/Excel) rawan kesalahan & manipulasi | Laporan tidak akurat, sulit diaudit |
| P2 | Banyak unit usaha tanpa sistem terintegrasi | Stok, kas, dan pendapatan tidak terpantau real-time |
| P3 | Perhitungan bunga, angsuran, dan SHU rumit | Salah hitung, sengketa anggota |
| P4 | Kewajiban pengembalian pinjaman modal Himbara | Risiko gagal bayar karena cashflow tidak terkontrol |
| P5 | Pelaporan ke Dinas Koperasi & Kementerian | Beban administrasi tinggi, keterlambatan |
| P6 | Transparansi terhadap anggota rendah | Kepercayaan & partisipasi anggota menurun |
| P7 | Tumpang tindih peran dengan BUMDes | Perlu pemisahan pembukuan yang jelas |

### 2.2 Peluang

- Standardisasi sistem untuk puluhan ribu koperasi desa yang seragam secara nasional.
- Potensi integrasi dengan ekosistem: Himbara, BULOG, agen pupuk/LPG 3kg, Pos Indonesia, sistem pembayaran (QRIS).
- Basis data ekonomi desa yang dapat mendukung pengambilan kebijakan.

---

## 3. Tujuan & Metrik Keberhasilan

### 3.1 Tujuan Produk (Goals)

1. **G1** — Menyediakan satu sistem untuk seluruh unit usaha koperasi (5 jenis koperasi).
2. **G2** — Mengotomasi pembukuan double-entry dan laporan keuangan sesuai standar koperasi.
3. **G3** — Memastikan ketertelusuran (auditability) seluruh transaksi.
4. **G4** — Mempermudah pelaporan kepada regulator dan bank penyalur.
5. **G5** — Meningkatkan transparansi & partisipasi anggota melalui akses mandiri (self-service).

### 3.2 Metrik Keberhasilan (Success Metrics / KPI)

| KPI | Target |
|---|---|
| Waktu tutup buku bulanan | < 1 hari kerja (dari sebelumnya berhari-hari) |
| Akurasi rekonsiliasi kas vs sistem | ≥ 99.5% |
| Adopsi anggota di aplikasi mobile | ≥ 60% anggota aktif dalam 6 bulan |
| Waktu pemrosesan pengajuan pinjaman | < 3 hari kerja |
| Ketepatan waktu laporan ke regulator | 100% sesuai tenggat |
| NPL (Non-Performing Loan) unit simpan pinjam | < 5% |
| Uptime sistem | ≥ 99.5% |

---

## 4. Pengguna & Persona (User Roles)

| Peran | Deskripsi | Akses Utama |
|---|---|---|
| **Super Admin / Pengelola Sistem** | Administrator platform (tingkat penyedia/koperasi induk) | Konfigurasi global, multi-tenant, audit |
| **Pengurus Koperasi (Ketua/Sekretaris/Bendahara)** | Manajemen koperasi sesuai AD/ART | Persetujuan, laporan, kebijakan |
| **Pengawas Koperasi** | Mengawasi jalannya koperasi | Akses baca laporan & log audit |
| **Manajer Unit Usaha** | Mengelola satu unit (gerai/apotek/klinik/dll) | Operasional unit, stok, kasir |
| **Kasir / Petugas Gerai** | Operasional harian penjualan | POS, transaksi penjualan |
| **Petugas Simpan Pinjam (Account Officer)** | Mengelola simpanan & pinjaman | Input simpanan, proses pinjaman |
| **Teller / Kasir Keuangan** | Transaksi tunai simpanan/angsuran | Setor, tarik, bayar angsuran |
| **Anggota Koperasi** | Anggota terdaftar | Lihat saldo, ajukan pinjaman, riwayat, belanja |
| **Calon Anggota** | Mendaftar keanggotaan | Registrasi, unggah dokumen |
| **Auditor / Regulator (read-only)** | Dinas Koperasi / pengawas eksternal | Ekspor laporan, akses audit trail |

---

## 5. Ruang Lingkup Produk

### 5.1 Pemetaan Jenis Koperasi → Unit Usaha KDMP

Sistem mendukung lima jenis koperasi sesuai klasifikasi perkoperasian Indonesia, yang dipetakan ke gerai/unit usaha KDMP:

| Jenis Koperasi | Modul Sistem | Unit Usaha KDMP Terkait |
|---|---|---|
| **Simpan Pinjam** | Modul USP (Unit Simpan Pinjam) | Unit Simpan Pinjam Desa |
| **Konsumen** | Modul Ritel & POS | Gerai Sembako, Apotek Desa |
| **Produsen** | Modul Produksi & Hasil Tani | Pengumpulan hasil tani, Cold Storage |
| **Jasa** | Modul Layanan/Jasa | Klinik Desa, Logistik/Distribusi, Agen (LPG, pupuk, BULOG, pembayaran) |
| **Serba Usaha (KSU)** | Lapisan integrasi semua modul | Kantor Koperasi mengelola seluruh gerai |

> Catatan: Tujuh gerai/unit yang umum pada KDMP mencakup Kantor Koperasi, Gerai Sembako, Apotek Desa, Klinik Desa, Unit Simpan Pinjam, Pergudangan/Cold Storage, serta Logistik/Distribusi.

### 5.2 In-Scope (Rilis Awal)

- Manajemen keanggotaan & badan hukum koperasi.
- Modul Simpan Pinjam lengkap (simpanan pokok/wajib/sukarela, pinjaman, angsuran, bunga/bagi hasil).
- Modul Ritel/POS untuk gerai sembako & konsumen.
- Modul Inventori & rantai pasok (pembelian, stok, gudang).
- Modul Akuntansi & pelaporan keuangan + SHU.
- Modul Jasa (layanan berbayar, agen, klinik dasar).
- Modul Produsen (penampungan hasil produksi anggota).
- Portal/aplikasi anggota.
- Dashboard & pelaporan regulator.

### 5.3 Out-of-Scope (Rilis Awal)

- Rekam medis elektronik (EMR) klinik yang kompleks — hanya pencatatan layanan & transaksi.
- Modul payroll/HR mendalam.
- Integrasi penuh perbankan inti (core banking) — hanya rekonsiliasi & antarmuka pembayaran.
- E-commerce publik antar-koperasi (fase lanjutan).

---

## 6. Kebutuhan Fungsional (Functional Requirements)

### 6.1 Modul Keanggotaan (Membership)

- **FR-MEM-01** Registrasi calon anggota dengan data identitas (NIK, alamat, kontak) dan verifikasi.
- **FR-MEM-02** Validasi NIK terhadap domisili desa/kelurahan (sesuai prinsip KDMP berbasis wilayah).
- **FR-MEM-03** Pengelolaan status keanggotaan (aktif, non-aktif, keluar, meninggal).
- **FR-MEM-04** Pencatatan simpanan pokok saat menjadi anggota.
- **FR-MEM-05** Kartu anggota digital (QR/barcode) untuk transaksi lintas unit.
- **FR-MEM-06** Riwayat lengkap aktivitas anggota (simpanan, pinjaman, belanja, SHU).
- **FR-MEM-07** Manajemen Rapat Anggota Tahunan (RAT): daftar hadir, kuorum, hasil keputusan.

### 6.2 Modul Simpan Pinjam (USP)

**Simpanan:**
- **FR-SP-01** Jenis simpanan: pokok, wajib, sukarela, berjangka (deposito koperasi).
- **FR-SP-02** Setoran & penarikan simpanan dengan validasi saldo & limit.
- **FR-SP-03** Perhitungan jasa simpanan (bunga/bagi hasil) otomatis berkala.
- **FR-SP-04** Auto-debit simpanan wajib bulanan.

**Pinjaman:**
- **FR-SP-05** Pengajuan pinjaman (online via anggota / input petugas).
- **FR-SP-06** Penilaian kelayakan (scoring sederhana: histori, kapasitas, agunan).
- **FR-SP-07** Workflow persetujuan berjenjang (petugas → pengurus → komite).
- **FR-SP-08** Skema bunga: flat, menurun (efektif/anuitas), dan **pola syariah** (murabahah/bagi hasil) sebagai opsi.
- **FR-SP-09** Pembuatan jadwal angsuran otomatis & akad/perjanjian.
- **FR-SP-10** Pembayaran angsuran, pelunasan dipercepat, denda keterlambatan.
- **FR-SP-11** Manajemen tunggakan & klasifikasi kolektibilitas (lancar, kurang lancar, macet).
- **FR-SP-12** Pencatatan agunan/jaminan.

### 6.3 Modul Ritel / POS (Koperasi Konsumen — Gerai Sembako & Apotek)

- **FR-POS-01** Point of Sale dengan scan barcode, multi-metode bayar (tunai, QRIS, potong saldo simpanan).
- **FR-POS-02** Harga khusus anggota vs non-anggota.
- **FR-POS-03** Penjualan kredit anggota (terhubung ke limit & buku piutang).
- **FR-POS-04** Manajemen shift kasir & rekonsiliasi laci kas.
- **FR-POS-05** Penjualan obat di apotek dengan kategori (bebas/terbatas) & pencatatan kedaluwarsa.
- **FR-POS-06** Cetak/Kirim struk (cetak & digital).
- **FR-POS-07** Mode offline-first dengan sinkronisasi saat online (penting untuk desa).

### 6.4 Modul Inventori & Rantai Pasok

- **FR-INV-01** Master produk dengan kategori, satuan, harga beli/jual, batch & expiry.
- **FR-INV-02** Manajemen stok multi-lokasi (gerai, gudang, cold storage).
- **FR-INV-03** Purchase Order ke pemasok / koperasi induk / BULOG.
- **FR-INV-04** Penerimaan barang (GRN) & retur.
- **FR-INV-05** Stock opname & penyesuaian stok.
- **FR-INV-06** Notifikasi stok minimum & barang mendekati kedaluwarsa.
- **FR-INV-07** Manajemen cold storage (suhu, kapasitas, hasil tani titipan).

### 6.5 Modul Produsen (Hasil Produksi Anggota)

- **FR-PRD-01** Pendaftaran komoditas anggota produsen (pertanian, perikanan, UMKM).
- **FR-PRD-02** Penampungan/pembelian hasil dari anggota dengan harga & timbangan.
- **FR-PRD-03** Penyimpanan di gudang/cold storage & traceability lot.
- **FR-PRD-04** Penjualan kolektif / distribusi ke pasar/offtaker.
- **FR-PRD-05** Bagi hasil ke anggota produsen.

### 6.6 Modul Jasa (Koperasi Jasa)

- **FR-JSA-01** Katalog layanan berbayar (logistik/antar sembako, sewa alat, pembayaran tagihan/PPOB).
- **FR-JSA-02** Layanan keagenan: LPG 3kg, pupuk bersubsidi, agen BULOG, agen bank (Laku Pandai).
- **FR-JSA-03** Pencatatan layanan klinik desa (kunjungan, tindakan dasar, tarif) — tanpa EMR kompleks.
- **FR-JSA-04** Penjadwalan & pelacakan order layanan (mis. pengantaran).

### 6.7 Modul Akuntansi & Keuangan

- **FR-ACC-01** Pembukuan double-entry dengan Chart of Accounts (CoA) standar koperasi.
- **FR-ACC-02** Jurnal otomatis dari setiap transaksi modul (POS, USP, dll).
- **FR-ACC-03** Buku besar, neraca, laporan laba rugi, arus kas.
- **FR-ACC-04** **Perhitungan & distribusi SHU otomatis** berdasarkan jasa simpanan & jasa usaha tiap anggota sesuai AD/ART.
- **FR-ACC-05** Manajemen kas & bank, rekonsiliasi rekening.
- **FR-ACC-06** Pembukuan terpisah per unit usaha (untuk menghindari tumpang tindih, mis. dengan BUMDes) namun terkonsolidasi.
- **FR-ACC-07** Modul pengembalian pinjaman modal program (Himbara): jadwal cicilan modal, alokasi, monitoring kewajiban.
- **FR-ACC-08** Manajemen aset tetap & penyusutan.

### 6.8 Modul Pelaporan & Dashboard

- **FR-RPT-01** Dashboard eksekutif (kas, penjualan, pinjaman, NPL, stok) real-time.
- **FR-RPT-02** Laporan keuangan periodik siap cetak/ekspor (PDF, Excel).
- **FR-RPT-03** Template laporan untuk Dinas Koperasi / Kementerian Koperasi.
- **FR-RPT-04** Laporan RAT (laporan pertanggungjawaban pengurus).
- **FR-RPT-05** Laporan kinerja per unit usaha.

### 6.9 Portal & Aplikasi Anggota

- **FR-APP-01** Lihat saldo simpanan & riwayat transaksi.
- **FR-APP-02** Ajukan pinjaman & pantau status.
- **FR-APP-03** Bayar angsuran / top-up simpanan (QRIS / transfer).
- **FR-APP-04** Belanja gerai (opsional) & lihat promo anggota.
- **FR-APP-05** Lihat estimasi & realisasi SHU.
- **FR-APP-06** Notifikasi (jatuh tempo, RAT, promo).

### 6.10 Administrasi & Keamanan Sistem

- **FR-SYS-01** Manajemen pengguna, peran, & hak akses (RBAC).
- **FR-SYS-02** Audit trail tak-terhapus untuk seluruh transaksi keuangan.
- **FR-SYS-03** Multi-tenant: satu platform melayani banyak koperasi desa.
- **FR-SYS-04** Konfigurasi parameter koperasi (bunga, biaya, AD/ART, formula SHU).
- **FR-SYS-05** Manajemen periode akuntansi & penutupan buku.

---

## 7. Kebutuhan Non-Fungsional (Non-Functional Requirements)

| Kategori | Kebutuhan |
|---|---|
| **Kinerja** | Transaksi POS < 2 detik; laporan standar < 5 detik |
| **Skalabilitas** | Arsitektur multi-tenant mendukung ribuan koperasi & jutaan anggota |
| **Ketersediaan** | Uptime ≥ 99.5%; mode offline untuk POS di area sinyal lemah |
| **Keamanan** | Enkripsi data sensitif (at-rest & in-transit), RBAC, MFA untuk pengurus |
| **Kepatuhan Data** | Sesuai UU PDP (Pelindungan Data Pribadi) No. 27/2022 |
| **Auditability** | Setiap perubahan data finansial tercatat (who/when/what) |
| **Lokalisasi** | Bahasa Indonesia, format Rupiah, zona waktu WIB/WITA/WIT |
| **Usability** | Antarmuka sederhana untuk pengguna awam teknologi di desa |
| **Konektivitas** | Hemat data, dukungan jaringan 3G/4G; sinkronisasi efisien |
| **Backup** | Pencadangan otomatis harian + disaster recovery |
| **Aksesibilitas** | Responsif (mobile-first), kontras & ukuran font memadai |

---

## 8. Kepatuhan Regulasi & Standar

Sistem harus dirancang agar selaras dengan kerangka hukum dan kebijakan berikut:

- **Inpres No. 9 Tahun 2025** — Percepatan pembentukan Koperasi Merah Putih (acuan program KDMP).
- **UU No. 25 Tahun 1992** tentang Perkoperasian — prinsip & tata kelola koperasi.
- **UU No. 4 Tahun 2023 (P2SK)** — pengaturan sektor keuangan yang memengaruhi usaha simpan pinjam.
- **Permenkop No. 8 Tahun 2023** — penyelenggaraan kegiatan usaha simpan pinjam oleh koperasi.
- **UU No. 27 Tahun 2022** tentang Pelindungan Data Pribadi.
- Ketentuan **perpajakan** koperasi (PPh badan, PPN untuk unit ritel sesuai ketentuan).
- Pedoman pelaporan **Kementerian Koperasi** & **Dinas Koperasi** daerah.
- Pemisahan tata kelola dengan **BUMDes** untuk menghindari tumpang tindih kewenangan.

> Catatan: Daftar regulasi bersifat acuan perancangan; validasi hukum final perlu dilakukan bersama penasihat hukum dan Dinas Koperasi setempat. _Konten telah diparafrasekan untuk kepatuhan lisensi._

---

## 9. Arsitektur & Pertimbangan Teknis (Tingkat Tinggi)

> Bagian ini bersifat rekomendasi awal; keputusan teknologi final akan ditetapkan pada fase desain teknis.

- **Pola arsitektur**: Multi-tenant, modular (modul dapat diaktifkan sesuai kebutuhan koperasi).
- **Klien**: Aplikasi web (pengurus/operasional) + aplikasi mobile (anggota) + POS offline-first.
- **Integrasi**: Gateway pembayaran/QRIS, API Himbara (rekonsiliasi & cicilan modal), PPOB, agen subsidi (LPG/pupuk), BULOG.
- **Pelaporan**: Mesin laporan dengan ekspor PDF/Excel & API untuk regulator.
- **Keamanan**: RBAC, audit log immutable, enkripsi, MFA.
- **Deployment**: Cloud dengan kemampuan operasi di konektivitas terbatas (sinkronisasi berkala).

### 9.1 Entitas Data Inti (Conceptual Data Model)

`Koperasi` → `UnitUsaha` → `Anggota` → `Simpanan` / `Pinjaman` / `Angsuran` → `Produk` / `Stok` / `TransaksiPenjualan` → `JurnalAkuntansi` → `SHU` → `LaporanRegulator`. Seluruh entitas finansial terhubung ke `AuditLog`.

---

## 10. Asumsi, Ketergantungan & Risiko

### 10.1 Asumsi
- Setiap koperasi desa memiliki badan hukum dan pengurus terlatih dasar.
- Tersedia perangkat (PC/tablet/printer) minimal di kantor koperasi.
- Konektivitas internet tersedia walau tidak selalu stabil.

### 10.2 Ketergantungan
- Kesiapan API mitra (Himbara, QRIS, BULOG, PPOB).
- Kebijakan & template pelaporan resmi dari Kementerian Koperasi.
- Pelatihan SDM koperasi (change management).

### 10.3 Risiko & Mitigasi

| Risiko | Dampak | Mitigasi |
|---|---|---|
| Literasi digital pengurus/anggota rendah | Adopsi lambat | UI sederhana, pelatihan, mode pendampingan |
| Konektivitas buruk di desa | Transaksi terganggu | Arsitektur offline-first + sinkronisasi |
| Gagal bayar pinjaman modal Himbara | Koperasi bangkrut | Dashboard cashflow & monitoring kewajiban modal |
| Tumpang tindih dengan BUMDes | Konflik kewenangan | Pembukuan terpisah & konsolidasi jelas |
| Penyalahgunaan dana (fraud) | Kerugian & hukum | Audit trail, approval berjenjang, hak akses ketat |
| Perubahan regulasi program | Rework | Desain konfigurabel & modular |

---

## 11. Roadmap & Rilis (Phased Delivery)

| Fase | Fokus | Modul Utama |
|---|---|---|
| **Fase 1 — Fondasi (MVP)** | Tata kelola inti & keuangan | Keanggotaan, Simpan Pinjam, Akuntansi dasar, Dashboard |
| **Fase 2 — Ritel & Inventori** | Operasional gerai | POS, Inventori, Apotek, Portal Anggota |
| **Fase 3 — Usaha Lanjutan** | Produsen & Jasa | Modul Produsen, Cold Storage, Jasa/Agen, Klinik |
| **Fase 4 — Integrasi & Skala** | Ekosistem & pelaporan | API Himbara/QRIS/BULOG, Pelaporan regulator otomatis, Multi-tenant skala nasional |
| **Fase 5 — Optimasi** | Analitik & kecerdasan | Credit scoring lanjutan, analitik ekonomi desa, rekomendasi |

---

## 12. Pertanyaan Terbuka (Open Questions)

1. Apakah skema bunga/bagi hasil mengikuti pola konvensional, syariah, atau keduanya per koperasi?
2. Format & frekuensi pelaporan resmi final ke Kementerian Koperasi seperti apa?
3. API/standar integrasi Himbara untuk monitoring cicilan modal — tersedia kapan?
4. Sejauh mana cakupan layanan klinik desa yang harus didukung sistem?
5. Apakah diperlukan sertifikasi/standar keamanan tertentu (mis. terkait usaha simpan pinjam/OJK)?
6. Model penyediaan: SaaS terpusat nasional, atau instans per kabupaten?

---

## 13. Lampiran — Glosarium

| Istilah | Arti |
|---|---|
| **KDMP** | Koperasi Desa/Kelurahan Merah Putih |
| **USP** | Unit Simpan Pinjam |
| **SHU** | Sisa Hasil Usaha (laba dibagikan ke anggota) |
| **KSU** | Koperasi Serba Usaha |
| **RAT** | Rapat Anggota Tahunan |
| **AD/ART** | Anggaran Dasar / Anggaran Rumah Tangga |
| **Himbara** | Himpunan Bank Milik Negara |
| **NPL** | Non-Performing Loan (pinjaman bermasalah) |
| **POS** | Point of Sale (kasir) |
| **PPOB** | Payment Point Online Bank (pembayaran tagihan) |
| **BUMDes** | Badan Usaha Milik Desa |
| **Kolektibilitas** | Klasifikasi kualitas pinjaman (lancar–macet) |

---

### Sumber Riset (Referensi)

- [ARMA Law — Koperasi Merah Putih: A National Strategy for Inclusive Growth (Inpres 9/2025)](https://arma-draft.squarespace.com/news-event/newsflash/koperasi-merah-putih-a-national-strategy-for-inclusive-growth)
- [Tempo — Prabowo Launches Over 80,000 Red-and-White Cooperatives](https://en.tempo.co/read/2030823/prabowo-launches-over-80000-red-and-white-cooperatives-108-already-operational)
- [Kompas — A Bitter Gift Called Red and White Village Cooperative (skema pembiayaan)](https://www.kompas.id/artikel/en-kado-pahit-itu-bernama-koperasi-desa-merah-putih)
- [Kompas — Worried About Overlapping with BUMDes](https://www.kompas.id/artikel/en-tugas-koperasi-desa-merah-putih-dikhawatirkan-tumpang-tindih-dengan-bumdes)
- [idnfinancials — Government Cuts Kopdes Merah Putih Development Target](https://www.idnfinancials.com/videos/watch/2737/government-cuts-50-kopdes-merah-putih-development-target)
- [Observer ID — KDMP and the Practice of Constitutional Economics](https://observerid.com/orchestrating-a-paradigm-shift-kdmp-and-the-practice-of-constitutional-economics/)

> _Seluruh ringkasan dari sumber eksternal telah diparafrasekan untuk kepatuhan terhadap pembatasan lisensi konten._
