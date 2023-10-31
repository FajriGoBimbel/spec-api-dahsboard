# API Spec

### MODUL SMBA

### AKSES

## TAMBAH ROLE

Request :

- Method : POST
- Endpoint : `/api/v1/role`,
- Header : null
- Body :

```json
{
  "namaRole": "string",
  "status": "string", // cth Aktif || Tidak Aktif
  "totalMenu": "number"
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

## EDIT NAMA ROLE

Request :

- Method : PUT
- Endpoint : `/api/v1/role`,
- Header : null
- Body :

```json
{
  "namaRole": "string",
  "status": "string", // cth Aktif || Tidak Aktif
  "totalMenu": "number"
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

## GET LIST ROLE SMBA

Request :

- Method : GET
- Endpoint : `/api/v1/roles/smba/${params.page}/${params.search}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "namaRole": "string",
      "status": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ],
  "count": "number",
  "page": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### PETUGAS

## TAMBAH PETUGAS

Request :

- Method : POST
- Endpoint : `/api/v1/petugas`,
- Header : null
- Body :

```json
{
  "nik": "string",
  "namaPetugas": "string",
  "role": "string"
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

## EDIT PETUGAS

Request :

- Method : PUT
- Endpoint : `/api/v1/petugas`,
- Header : null
- Body :

```json
{
  "nik": "string",
  "namaPetugas": "string",
  "role": "string"
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

## GET LIST PETUGAS

Request :

- Method : GET
- Endpoint : `/api/v1/petugas/${params.page/${params.search}}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "nik": "string",
      "namaPetugas": "string",
      "role": "string",
      "status": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ],
  "count": "number",
  "page": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### MASTER

### MATA PELAJARAN

## TAMBAH MATA PELAJARAN

Request :

- Method : POST
- Endpoint : `/api/v1/mapel`,
- Header : null
- Body :

```json
{
  "mataPelajaran": "string",
  "singkatan": "string",
  "utbk": "boolean",
  "status": "string"
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

## EDIT MATA PELAJARAN

Request :

- Method : PUT
- Endpoint : `/api/v1/mapel`,
- Header : null
- Body :

```json
{
  "mataPelajaran": "string",
  "singkatan": "string",
  "utbk": "boolean",
  "status": "string"
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

## GET LIST MATA PELAJARAN

Request :

- Method : GET
- Endpoint : `/api/v1/mapel/${params.page/${params.search}}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "mataPelajaran": "string",
      "singkatan": "string",
      "utbk": "boolean",
      "status": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ],
  "count": "number",
  "page": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### KURIKULUM

## TAMBAH KURIKULUM

Request :

- Method : POST
- Endpoint : `/api/v1/kurikulum`,
- Header : null
- Body :

```json
{
  "namKurikulum": "string",
  "singkatan": "string",
  "tahunTerbit": "string, date",
  "tanggalAwal": "string, date",
  "tanggalAkhir": "string, date",
  "status": "string"
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

## EDIT Kurikulum

Request :

- Method : PUT
- Endpoint : `/api/v1/kurikulum`,
- Header : null
- Body :

```json
{
  "namKurikulum": "string",
  "singkatan": "string",
  "tahunTerbit": "string, date",
  "tanggalAwal": "string, date",
  "tanggalAkhir": "string, date",
  "status": "string"
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

## GET LIST KURIKULUM

Request :

- Method : GET
- Endpoint : `/api/v1/kurikulum/${params.page/${params.search}}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "namKurikulum": "string",
      "singkatan": "string",
      "tahunTerbit": "string, date",
      "tanggalAwal": "string, date",
      "tanggalAkhir": "string, date",
      "status": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ],
  "count": "number",
  "page": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### BAB

## GET UPLINE WITH BY MAPEL

Request :

- Method : GET
- Endpoint : `/api/v1/upline/${params.idMapel}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "kodeUpline": "string",
      "namaTeoriUpline": "string",
      "status": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ],
  "count": "number",
  "page": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## TAMBAH BAB

Request :

- Method : POST
- Endpoint : `/api/v1/bab`,
- Header : null
- Body :

```json
{
  "mataPelajaran": "string, mandatory",
  "upline": "string, mandatory",
  "kodeBab": "string, mandatory",
  "namBab": "string, mandatory",
  "peluang": "string, mandatory" // sering, normal, jarang
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

## EDIT BAB

Request :

- Method : PUT
- Endpoint : `/api/v1/bab`,
- Header : null
- Body :

```json
{
  "mataPelajaran": "string, mandatory",
  "upline": "string, mandatory",
  "kodeBab": "string, mandatory",
  "namBab": "string, mandatory",
  "peluang": "string, mandatory",
  "status": "string"
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

## GET LIST BAB

Request :

- Method : GET
- Endpoint : `/api/v1/bab/${params.page/${params.search}}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "namaBab": "string",
      "peluang": "string",
      "status": "string",
      "subBab": [
        {
          "id": "string",
          "namSubBab": "string"
        }
      ],
      "createdAt": "date",
      "updatedAt": "date"
    }
  ],
  "count": "number",
  "page": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### SILABUS

## GET TAHUN AJARAN

Request :

- Method : GET
- Endpoint : `/api/v1/tahunAjaran`,
- Header : null
- Body : null

- Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "tahunAjaran": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## GET TINGKAT KELAS

Request :

- Method : GET
- Endpoint : `/api/v1/tingkatkelas`,
- Header : null
- Body : null

- Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "tingkatKelas": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## GET Layanan

Request :

- Method : GET
- Endpoint : `/api/v1/jenislayanan`,
- Header : null
- Body : null

- Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "jenisLayanan": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## GET KELOMPOK UJIAN

Request :

- Method : GET
- Endpoint : `/api/v1/kelompokujian`,
- Header : null
- Body : null

- Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "nama": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## MATA AJAR

## TAMBAH MATA AJAR

Request :

- Method : POST
- Endpoint : `/api/v1/mata-ajar`,
- Header : null
- Body :

```json
{
  "mataAjar": "string",
  "singkatan": "string",
  "upline": "string, date",
  "status": "string"
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

## EDIT MATA AJAR

Request :

- Method : PUT
- Endpoint : `/api/v1/mata-ajar`,
- Header : null
- Body :

```json
{
  "mataAjar": "string",
  "singkatan": "string",
  "upline": "string, date",
  "status": "string"
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

## GET LIST MATA AJAR

Request :

- Method : GET
- Endpoint : `/api/v1/mata-ajar/${params.page/${params.search}}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "idBab": "number",
      "namaMataAjar": "string",
      "singkatan": "string",
      "subBab": [
        {
          "id": "string",
          "namSubBab": "string"
        }
      ],
      "status": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ],
  "count": "number",
  "page": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### SOAL

## SUMBER SOAL

## GET JENIS SUMBER SOAL

Request :

- Method : GET
- Endpoint : `/api/v1/jenissumbersoal`,
- Header : null
- Body : null

- Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "nama": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## TAMBAH SUMBER SOAL

Request :

- Method : POST
- Endpoint : `/api/v1/mata-ajar`,
- Header : null
- Body :

```json
{
  "jenisSumber": "string",
  "namaSumber": "string"
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

## EDIT SUMBER SOAL

Request :

- Method : PUT
- Endpoint : `/api/v1/sumber-soal`,
- Header : null
- Body :

```json
{
  "jenisSumber": "string",
  "namaSumber": "string"
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

## GET LIST SUMBER SOAL

Request :

- Method : GET
- Endpoint : `/api/v1/sumber-soal/${params.page/${params.search}}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "idBab": "number",
      "namaMataAjar": "string",
      "singkatan": "string",
      "subBab": [
        {
          "id": "string",
          "namSubBab": "string"
        }
      ],
      "status": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ],
  "count": "number",
  "page": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
