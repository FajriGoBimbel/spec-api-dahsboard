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

// add
{
  "IdZona": 911,
  "NamaZona": "ZONA TEST 3",
  "Gedung": [1488, 1487],
  "IdPenanda": "306"
}

// edit zona
// hapus gedung dari zona
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
