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
  "isUtbk": "boolean",
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
- Endpoint : `/api/v1/mapel/${params.idMapel}`,
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
- Endpoint : `/api/v1/mapel/${params.page}/${params.search}`,
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
      "isUtbk": "boolean",
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

## GET DETAIL MATA PELAJARAN

Request :

- Method : GET
- Endpoint : `/api/v1/mapel/${params.idMapel}`,
- Header : null
- Body : null

Response :

```json
{
  "data": {
    "id": "string",
    "mataPelajaran": "string",
    "singkatan": "string",
    "isUtbk": "boolean",
    "status": "string",
    "createdAt": "date",
    "updatedAt": "date"
  },

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## DELETE BY ID MATA PELAJARAN

Request :

- Method : DELETE
- Endpoint : `/api/v1/mapel/${params.idMapel}`,
- Header : null
- Body : null

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

## GET DETAIL KURIKULUM

Request :

- Method : PUT
- Endpoint : `/api/v1/kurikulum/${params.idKurikulum}`,
- Header : null
- Body : null

Response :

```json
{
  "data": {
    "id": "string",
    "namKurikulum": "string",
    "singkatan": "string",
    "tahunTerbit": "string, date",
    "tanggalAwal": "string, date",
    "tanggalAkhir": "string, date",
    "status": "string",
    "createdAt": "date",
    "updatedAt": "date"
  },

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### BAB

<!--
## GET LIST BAB BERDASARKAN MAPEL

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
``` -->

## TAMBAH BAB

Request :

- Method : POST
- Endpoint : `/api/v1/bab`,
- Header : null
- Body :

```json
{
  "kurikulum": "string",
  "tingkatKelas": "string",
  "namSekolahKelas": "string",
  "mataPelajaran": "string, mandatory",
  "bab": "string, mandatory",
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
  "kurikulum": "string",
  "tingkatKelas": "string",
  "namSekolahKelas": "string",
  "mataPelajaran": "string, mandatory",
  "bab": "string, mandatory",
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

## GET LIST BAB

Request :

- Method : GET
- Endpoint : `/api/v1/bab/${params.page}/${params.search}/${params.mapel}`,
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

## GET DETAIL BAB

Request :

- Method : GET
- Endpoint : `/api/v1/bab/${params.idBab}`,
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
      "tingkatKelas": "string" // cth 12 SMA IPS
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## GET Layanan/JENIS KELAS

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

## TAMBAH SILABUS

Request :

- Method : POST
- Endpoint : `/api/v1/silabus`,
- Header : null
- Body :

```json
{
  "tahunAjaran": "string",
  "kurikulum": "string",
  "tingkatKelas": "string",
  "jenisLayanan": "string",
  "kelompokUjian": "string",
  "jumlahPertemuan": "number",
  "semester": "number",
  "mataPelajaran": "string",
  "pertemuan": "Array of obj"
}
```

- Response :

```json
{
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## GET LIST SILABUS

Request :

- Method : GET
- Endpoint : `/api/v1/silabus`,
- Header : null
- Body : null

- Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "namSilabus": "string",
      "namKurikulum": "string",
      "tingkatKelas": "string",
      "jenisLayanan": "string",
      "namaKelompokUjian": "string",
      "jumlahPertemuan": "number",
      "jumlahEntri": "number",
      "status": "string"
    }
  ],
  "page": "number",
  "count": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## GET DETAIL SILABUS

Request :

- Method : GET
- Endpoint : `/api/v1/silabus`,
- Header : null
- Body : null

- Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "namSilabus": "string",
      "namKurikulum": "string",
      "tingkatKelas": "string",
      "jenisLayanan": "string",
      "namaKelompokUjian": "string",
      "jumlahPertemuan": "number",
      "jumlahEntri": "number",
      "status": "string",
      "pertemuan": [
        {
          "listBab": [
            {
              "id": "string",
              "namadankodebab": "string"
            }
          ]
        }
      ]
    }
  ],
  "page": "number",
  "count": "number",

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### MATA AJAR

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
  "upline": "string",
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
- Endpoint : `/api/v1/mata-ajar/${params.page}/${params.search}`,
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

## GET DETAIL MATA AJAR

Request :

- Method : GET
- Endpoint : `/api/v1/mata-ajar/${params.idMatAjar}}`,
- Header : null
- Body : null

Response :

```json
{
  "data": {
    "id": "string",
    "idBab": "number",
    "namaMataAjar": "string",
    "singkatan": "string",
    "status": "string",
    "createdAt": "date",
    "updatedAt": "date"
  },

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
- Endpoint : `/api/v1/sumber-soal`,
- Header : null
- Body :

```json
{
  "jenisSumber": "string",
  "namaSumber": "string",
  "status": "string,
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
  "namaSumber": "string",
  "status": "string,
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
      "jenisSumber": "string",
      "namaSumber": "string",
      "detailTo": "number",
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

## GET DETAIL ISI KODE SUMBER

Request :

- Method : GET
- Endpoint : `/api/v1/kode-sumber/${params.idSumberSoal}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "smt": "string",
      "kodeSoal": "string",
      "tahun": "date",
      "tingkatKelas": "string",
      "jenisInstitusi": "string",
      "provinsi": "string",
      "kota": "string",
      "institusi": "string",
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

### WACANA

## GET LIST WACANA

Request :

- Method : GET
- Endpoint : `/api/v1/wacana/${params.mapel}/${params.keywoard}/${params.judulWacana}`, <!-- PARAM AKTIF SETELAH PILIH MAPEL, JIKA TIDAK PILIH MAPEL GET ALL LIST -->
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "mataPelajaran": "string",
      "judulWacana": "string",
      "cuplikanTeks": "string",
      "keyword": "string",
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

## GET DETAIL WACANA

Request :

- Method : GET
- Endpoint : `/api/v1/wacana/${params.idWacana}`,
- Header : null
- Body : null

Response :

```json
{
  "data": {
    "id": "string",
    "judulWacana": "string",
    "mataPelajaran": "string",
    "cuplikanTeks": "string",
    "keyword": "string",
    "createdAt": "date",
    "updatedAt": "date"
  },

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## TAMBAH WACANA

Request :

- Method : POST
- Endpoint : `/api/v1/wacana`,
- Header : null
- Body :

```json
{
  "cuplikanTeks": "string",
  "judulWacana": "string",
  "keyword": "string",
  "mataPelajaran": "string"
}
```

Response :

```json
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## UPDATE WACANA

Request :

- Method : PUT
- Endpoint : `/api/v1/wacana/${params.idWacana}`,
- Header : null
- Body :

```json
{
  "cuplikanTeks": "string",
  "judulWacana": "string",
  "keyword": "string",
  "mataPelajaran": "string"
}
```

Response :

```json
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## HAPUS WACANA

Request :

- Method : DELETE
- Endpoint : `/api/v1/wacana/${params.idWacana}`,
- Header : null
- Body : null

Response :

```json
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## UPLOAD VIDEO

Request :

- Method : POST
- Endpoint : `/api/v1/wacana/${params.idWacana}`,
- Header : null
- Body :

```json
{
  "ambilVideo": "string",
  "judulVideo": "string",
  "deskripsi": "string",
  "keyword": "string",
  "idSoal": "string"
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

### KUNCI JAWABAN

## GET JENIS PRODUK

Request :

- Method : GET
- Endpoint : `/api/v1/jenis-produk`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "idProduk": "string",
      "namaProduk": "string"
    }
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## GET KODE PAKET

Request :

- Method : GET
- Endpoint : `/api/v1/kode-paket`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "idProduk": "string",
      "namaPaket": "string"
    }
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## GET LIST KUNCI JAWABAN

Request :

- Method : GET
- Endpoint : `/api/v1/kunci-jawaban/${params.jenisProduk}/${params.kelompokUjian}/${params.kodePaket}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "noUrut": "number",
      "idSoal": "string",
      "kelompokUjian": "string",
      "bab": "string",
      "kodeSumber": "string",
      "tipeSoal": "string",
      "level": "string",
      "kunciJawaban": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
