# API SPEC MODULE IDPP AKADEMIK

## Home

### get gedung per zona

Request

- Method : POST
- Endpoint : `api/v1/idpp/list/gedungperzona`
- Body :

```json
{
  "IdZona": "8"
}
```

Response

```json
{
  "data": [
    {
      "IdZona": 8,
      "IdGedung": 3,
      "NamaGedung": "PW 31"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### get dashboard

Request

- Method : POST
- Endpoint : `api/v1/idpp/dashboard`
- Body :

```json
{
  "idGedung": "3"
}
```

Response

```json
{
  "data": [
    {
      "Tanggal": "2023-11-10",
      "Hari": "JUMAT",
      "Legend": "JUMAT<br>(10/11)",
      "Draft": 0,
      "Jadwal": 0,
      "Rencana": 0,
      "Realisasi": 15,
      "RealisasiPengajar": 0,
      "Cancel": 1
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Master

### Jenis Kerja

#### get jenis kerja

Request :

- Method : POST
- Endpoint : `api/v1/idpp/jeniskerja/get?search=${namajeniskerja}&page=${page}&limit=${limit}`

Response :

```json
{
  "data": [
    {
      "IdJenisKerja": "0201",
      "NamaJenisKerja": "Mengajar",
      "NamaJenisKerjaSiswa": "Mengajar",
      "NamaJenisKerjaPetugas": "Mengajar",
      "NamaJenisKerjaPengajar": "Mengajar",
      "Info1": "Kelas",
      "Info2": "Pelajaran",
      "Info3": "Pertemuan"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  },
  "pagination": {
    "page": 1,
    "limit": 10,
    "totalData": 2,
    "totalPage": 1
  }
}
```

#### Add / Ubah /soft delete jenis kerja

Request :

- Method : POST
- Endpoint : `api/v1/idpp/jeniskerja/set?params=${params}`
- Body :

> **_NOTE:_** NamaJenisKerjaSiswa,NamaJenisKerjaPetugas,NamaJenisKerjaPengajar = NamaJenisKerja

```json
//add
{
  "namajeniskerja": "string"
}

//edit
{
  "IdJenisKerja": "string",
  "namajeniskerja": "string"
}

// soft delete
{
  "IdJenisKerja": "string",
  "status": "TidakAktif"
}
```

Response :

```json
{
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Kegiatan

#### get list jenis petugas

Request :

- Method : POST
- Endpoint : `api/v1/idpp/list/jenispetugas`

Response :

```json
{
  "data": [
    {
      "IdJenisPetugas": 4,
      "NamaJenisPetugas": "Keuangan"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get kegiatan

Request :

- Method : POST
- Endpoint : `api/v1/idpp/kegiatan/get?search=${NamaJenisKerja|NamaKegiatan|DasarPenggajian|NamaJenisPetugas}&sortby=${NamaJenisKerja|NamaKegiatan|DasarPenggajian|NamaJenisPetugas|WaktuMinimal|WaktuMaximal|Pengali|PengaliSD|IsRelatif|PK|PH|PF}&sort=${asc|desc}&page=${page}&limit=${limit}`

Response :

```json
{
  "data": [
    {
      "IdJenisKerja": "0201",
      "NamaJenisKerja": "Mengajar",
      "NamaJenisKerjaSiswa": "Mengajar",
      "NamaJenisKerjaPetugas": "Mengajar",
      "NamaJenisKerjaPengajar": "Mengajar",
      "Info1": "Kelas",
      "Info2": "Pelajaran",
      "Info3": "Pertemuan",
      "IdKegiatan": "020110",
      "NamaKegiatan": "KBM Virtual",
      "NamaKegiatanSiswa": "KBM Virtual",
      "NamaKegiatanPetugas": "KBM Virtual",
      "NamaKegiatanPengajar": "KBM Virtual",
      "DasarPenggajian": "BOM",
      "WaktuMinimal": "45",
      "WaktuMaximal": "90",
      "Pengali": "1",
      "PengaliSD": "0.5",
      "IsRelatif": "N",
      "IdJenisPetugas": "1",
      "PK": "false",
      "PH": "true",
      "PF": "true",
      "KR": "false",
      "NamaJenisPetugas": "BOP"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get dasar penggajian

Request :

- Method : POST
- Endpoint : `api/v1/idpp/list/dasarpenggajian?search=${dasarPengajian}`

Response :

```json
{
  "id": "string",
  "dasarPengajian": "string"
}
```

#### add / edit / soft delete kegiatan

Request :

- Method : POST
- Endpoint : `api/v1/idpp/kegiatan/set?param=${param}`
- Body :

```json
{
  "Idkegiatan": 0,
  "IdJenisKerja": "0236",
  "NamaKegiatanSiswa": "TEST",
  "NamaKegiatanPetugas": "TEST",
  "NamaKegiatanPengajar": "TEST",
  "DasarPenggajian": "BOM",
  "Pengali": 1,
  "IsRelatif": "Y",
  "PK": "true",
  "PH": "true",
  "PF": "true",
  "KR": "true",
  "IdJenisPetugas": "14",
  "PengaliSD": 1,
  "WaktuMinimal": 120,
  "WaktuMaximal": 120
}

// soft delete
{
  "idkegiatan" : "number",
  "status" : "TidakAktif"
}
```

Response :

```json
{
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Zona

#### get gedung per kota go

Request :

- Method : POST
- Endpoint : `api/v1/idpp/list/gedungperkotago?search=${namagedung}`
- Body :

```json
{
  "idpenanda": "6"
}
```

Response :

```json
{
  "data": [
    {
      "IdGedung": 225,
      "NamaGedung": "MAWAR 12"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get zona by kota

Request :

- Method : POST
- Endpoint : `api/v1/idpp/zona/get?sortby=${NamaZona|BanyakGedung|Status|NamaGedung}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "idPenanda": "6"
}
```

Response :

```json
{
  "data": [
    {
      "IdZona": 31,
      "NamaZona": "Surakarta Zona 1",
      "IdPenanda": 6,
      "Penanda": "SURAKARTA",
      "BanyakGedung": 4,
      "Status": "Y",
      "Gedung": "[{\"IdGedung\": 315, \"IdPenanda\": 6, \"NamaGedung\": \"BHAYANGKARA 40A\", \"NamaPenanda\": \"SURAKARTA\"}, {\"IdGedung\": 227, \"IdPenanda\": 6, \"NamaGedung\": \"VETERAN 234 TIPES\", \"NamaPenanda\": \"SURAKARTA\"}, {\"IdGedung\": 581, \"IdPenanda\": 6, \"NamaGedung\": \"SLAMET RIYADI 430\", \"NamaPenanda\": \"SURAKARTA\"}, {\"IdGedung\": 887, \"IdPenanda\": 6, \"NamaGedung\": \"SLAMET RIYADI 463\", \"NamaPenanda\": \"SURAKARTA\"}]"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### add / edit /delete zona

Request :

- Method : POST
- Endpoint : `api/v1/idpp/zona/set?param=${param}`
- Body :

```json

// add zona harus ada gedung 1:1
{
  "IdZona": 911,
  "NamaZona": "ZONA TEST 3",
  "Gedung": [1488, 1487],
  "IdPenanda": "306"
}

// edit zona
// bisa nambah gedung
// bisa hapus gedung dari zona
{
  "IdZona": 911,
  "NamaZona": "ZONA TEST 3 EDIT",
  "Gedung": [1488],
  "IdPenanda": "306"
}

//hard delete
{
  "IdZona": 911
}
```

Response :

```json
{
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Petugas

#### get petugas

Request :

- Method : POST
- Endpoint : `api/v1/idpp/petugas/get?sortby=${NIK|NamaLengkap|Username|NamaJenisPetugas|JumlahHariBuka|JumlahHariDepanBuka|TanggalAwalTutup|TanggalAkhirTutup}&sort=${asc|desc}`
- Body :

```json
{
  "IdPenanda": "6",
  "IdZona": "31"
}
```

Response :

```json
{
  "data": [
    {
      "NIK": "0902500170",
      "NamaLengkap": "AGITYA PUTRA KUSUMA",
      "IdJenisPetugas": 5,
      "Username": "0902500170",
      "Password": "23baf8622a8af9f2e23cd40cdf6d7b9e",
      "Verifikasi": "T",
      "StatusLogin": "F",
      "JumlahHariBuka": "15",
      "JumlahHariDepanBuka": "0",
      "TanggalAwalTutup": "2020-01-01",
      "TanggalAkhirTutup": "2020-05-01",
      "Menu": "[5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 44, 45, 58]",
      "IdZona": 31,
      "NamaZona": "Surakarta Zona 1",
      "IdPenanda": 6,
      "Penanda": "SURAKARTA",
      "IdGedung": 315,
      "NamaGedung": "BHAYANGKARA 40A",
      "NamaJenisPetugas": "Petugas Pembuat Jadwal (PPJ)",
      "IdPenandaZona": 6,
      "NamaPenandaZona": "SURAKARTA"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get petugas per gedung

Request :

- Method : POST
- Endpoint : `api/v1/idpp/list/petugasPerGedung`
- Body :

```json
{
  "IdGedung": "315"
}
```

Response :

```json
{
  "data": [
    {
      "NIK": "2018166067",
      "NIKNama": "2018166067 Anggi Fajar Setyawan (KR)"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Kelompok Waktu

#### get kelompok waktu by tahun ajaran

Request :

- Method : POST
- Endpoint : `api/v1/idpp/kelompokwaktu/get?sortby=${TanggalAwal|TanggalAkhir|KelompokWaktuSD|KelompokWaktuNONSD}&sort=${asc|desc}`
- Body :

```json
{
  "TahunAjaran": "2024/2025"
}
```

Response :

```json
{
  "data": [
    {
      "IdKelompokWaktu": 6278,
      "TanggalAwal": "2023-06-25",
      "TanggalAkhir": "2024-07-06",
      "Periode": "25 Jun 2023 - 06 Jul 2024",
      "KelompokWaktuSD": 56,
      "KelompokWaktuNONSD": 56,
      "Data": "[{\"Awal\": \"06:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708921, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708928, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708935, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708942, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708949, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708956, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708963, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708970, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708922, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708929, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708936, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708943, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708950, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708957, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708964, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708971, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708923, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708930, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708937, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708944, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708951, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708958, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708965, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708972, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708924, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708931, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708938, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708945, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708952, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708959, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708966, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708973, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708925, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708932, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708939, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708946, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708953, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708960, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708967, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708974, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708926, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708933, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708940, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708947, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708954, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708961, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708968, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708975, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708927, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708934, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708941, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708948, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708955, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708962, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"1\", \"IdDetail\": 708969, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"SD\", \"Shift\": \"2\", \"IdDetail\": 708976, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708977, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708984, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708991, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708998, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709005, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709012, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709019, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Senin\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709026, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708978, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708985, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708992, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708999, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709006, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709013, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709020, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Selasa\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709027, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708979, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708986, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708993, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709000, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709007, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709014, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709021, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Rabu\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709028, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708980, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708987, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708994, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709001, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709008, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709015, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709022, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Kamis\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709029, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708981, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708988, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708995, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709002, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709009, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709016, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709023, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Jumat\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709030, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708982, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708989, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708996, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709003, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709010, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709017, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709024, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Sabtu\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709031, \"Default\": 1}, {\"Awal\": \"06:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Pagi\", \"Akhir\": \"09:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708983, \"Default\": 1}, {\"Awal\": \"09:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Pagi\", \"Akhir\": \"12:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 708990, \"Default\": 1}, {\"Awal\": \"12:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Siang\", \"Akhir\": \"13:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 708997, \"Default\": 1}, {\"Awal\": \"13:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Siang\", \"Akhir\": \"15:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709004, \"Default\": 1}, {\"Awal\": \"15:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Sore\", \"Akhir\": \"17:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709011, \"Default\": 1}, {\"Awal\": \"17:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Sore\", \"Akhir\": \"19:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709018, \"Default\": 1}, {\"Awal\": \"19:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Malam\", \"Akhir\": \"21:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"1\", \"IdDetail\": 709025, \"Default\": 1}, {\"Awal\": \"21:00:00.000000\", \"Hari\": \"Minggu\", \"Sesi\": \"Malam\", \"Akhir\": \"23:00:00.000000\", \"Level\": \"NON SD\", \"Shift\": \"2\", \"IdDetail\": 709032, \"Default\": 1}]"
    }
  ]
}
```

### Jadwal Pengajar

#### get list pengajar per gedung

Request :

- Method : POST
- Endpoint : `api/v1/idpp/list/pengajarpergedung`
- Body :

```json
{
  "IdGedung": "1384"
}
```

Response :

```json
{
  "data": [
    {
      "StatusPengajar": "PH",
      "IsSD": "NON SD",
      "NIK": "2019239373",
      "NIKNama": "2019239373 Nathan (PH)"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get jadwal pengajar

Request

- Method : POST
- Endpoint : `api/v1/idpp/jadwalpengajar/get?sortby=${ALL}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "IdGedung": "3",
  "TahunAjaran": "2023/2024"
}
```

Response :

```json
{
  "data": [
    {
      "NIK": "2022267427",
      "NamaLengkap": "Abdullah Rasyid Daelani",
      "TanggalAwal": "2023-06-25",
      "TanggalAkhir": "2024-07-06",
      "IdKelompokWaktu": 6278,
      "Periode": "25 Jun 2023 - 06 Jul 2024",
      "Level": "NONSD",
      "NIKNama": "2022267427 - Abdullah Rasyid Daelani (PH)",
      "Senin": "17:00:00",
      "Selasa": "17:00:00",
      "Rabu": "17:00:00",
      "Kamis": "17:00:00",
      "Jumat": "17:00:00",
      "Sabtu": "17:00:00",
      "Minggu": "00:00:00"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  },
  "pagination": {
    "page": 1,
    "limit": 10,
    "totalData": 2,
    "totalPage": 1
  }
}
```

#### get jadwal pengajar detail

Request :

- Method : POST
- Endpoint : `api/v1/idpp/jadwalpengajar/getdetail`
- Body :

```json
{
  "Id": "6278",
  "NIK": "2019239373",
  "Level": "NON SD"
}
```

Response

```json
{
  "data": [
    {
      "Sesi": "Pagi",
      "Shift": "1",
      "IdKelompokWaktuDetail": 708977,
      "Hari": "Senin",
      "JamAwal": "06:00:00",
      "JamAkhir": "09:00:00",
      "IsJadwal": 0,
      "IsDefaultJadwal": 1,
      "Durasi": "03:00:00"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Pengali Kerja Sama

#### get pengali kerja sama

Request :

- Method : POST
- Endpoint : `api/v1/idpp/pengalikerjasama/get?sortby=${NamaGedung|Provinsi|District|NoMOU|NamaSekolah|Pengali}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "TahunAjaran": "2021/2022"
}
```

Response :

```json
{
  "data": [
    {
      "Pengali": 0,
      "IdGedung": 1384,
      "NamaGedung": "PW 33",
      "TahunAjaran": "2021/2022",
      "IdProvinsi": 2,
      "Provinsi": "PROVINSI SUMATERA UTARA",
      "IdDistrict": 40,
      "District": "KABUPATEN KARO",
      "IdSekolah": 102340,
      "NamaSekolah": "SMA Katolik Kabanjahe",
      "NoMOU": ""
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Pengali Luar Kota

#### get pengali luar kota

Request :

- Method : POST
- Endpoint : `api/v1/pengaliluarkota/get`
- Body :

```json
{
  "Idkota": "string"
}
```

Response

```json
{
  "data": [{}],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Silabus Kelas

#### get list pelajaran

Request :

- Method : POST
- Endpoint : `api/v1/idpp/list/pelajaran`

Response :

```json
{
  "data": [
    {
      "IdPelajaran": 1,
      "NamaPelajaran": "MATEMATIKA"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get list kelas per gedung, tingkat kelas dan tahun ajaran

Request :

- Method : POST
- Endpoint : `api/v1/idpp/list/kelaspergedungtingkatkelastahunajaran`
- Body :

```json
{
  "TahunAjaran": "2021/2022",
  "TingkatKelas": "9",
  "Gedung": "1384"
}
```

Response :

```json
{
  "data": [
    {
      "IdKelas": 231435,
      "NamaKelas": "9-SMP-P-N-UJI COBA",
      "TanggalRunning": "2021-08-04",
      "SingkatanLayanan": "P",
      "JenisKelasSilabus": "PLATINUM",
      "Singkatan": "P",
      "TingkatKelas": "9",
      "KelompokSekolah": "SMP",
      "Jurusan": "UMUM",
      "TingkatSekolah": "9 SMP UMUM",
      "TahunAjaran": "2021/2022"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get silabus kelas

Request :

- Method : POST
- Endpoint : `api/v1/idpp/silabuskelas/get`
- Body :

```json
{
  "Gedung": "1384",
  "TingkatKelas": "9",
  "TahunAjaran": "2021/2022",
  "Kelas": "231435",
  "KelompokSekolah": "SMP",
  "Jurusan": "UMUM"
}
```

Response :

```json
{
  "data": [
    {
      "IdPelajaran": 9,
      "NamaPelajaran": "EKONOMI",
      "Semester": 1,
      "IdKelas": "",
      "KodeSilabus": "",
      "StatusSilabusKelas": "BELUM"
    }
  ]
}
```
