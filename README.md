graph TD
    %% Warna Node
    classDef start end fill:#f9f,stroke:#333,stroke-width:2px;
    classDef process fill:#bbf,stroke:#333,stroke-width:1px;
    classDef approval fill:#fbf,stroke:#333,stroke-width:1px;
    
    A([1. Administrasi: Buat Surat Permohonan]) --> B{Kategori?}
    B -->|IT / AC / Medis| C[2. Pembelian: Minta & Input Harga Vendor]
    C --> D[3. Suster: Review & Tambah Catatan]
    D --> E[4. Pembelian: Buat Draf PO]
    
    E --> F{Hierarki Persetujuan}
    F -->|Tahap 1| G[5. Kepala Bagian: TTE ACC Teknis]
    G -->|Tahap 2| H[6. Suster: TTE & Stempel Digital]
    
    H --> I([7. Sistem: Generate PDF PO Sah])
    I --> J[8. Pembelian: Kirim PO ke Vendor]
    J --> K[9. Vendor: Datang bawa Barang/Servis + Surat Jalan]
    
    K --> L[10. Teknisi: Cek Barang/Jasa & Upload Surat Jalan]
    L --> M{Kategori?}
    M -->|Barang| N[11a. Sistem: Generate Berita Acara]
    M -->|Jasa| O[11b. Sistem: Generate Laporan Kerja]
    
    N --> P[12. Keuangan: Validasi Dokumen Lengkap]
    O --> P
    P --> Q([13. Keuangan: Cetak Bukti Bayar])
