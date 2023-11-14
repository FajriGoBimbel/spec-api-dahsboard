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

- Method : PUT
- Endpoint : `/api/v1/akses/roles/status`
- Header : null
- Body :

```json
{
  "id": "number",
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

### tambah role

- Method : POST
- Endpoint : `/api/v1/akses/roles`
- Header : null
- Body :

```json
{
  "nama": "string"
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

## Akses Petugas

### get all

Request

- Method : GET
- Endpoint : `/api/v1/akses/petugas?sortby=${id|nama|namarole|status|akundefault}&sort=${asc|desc}&page=${page}&limit=${limit}`

Response

```json
{
  "data": [
    {
      "id": "string",
      "nama": "string",
      "idrole": "number",
      "namarole": "string",
      "status": "string",
      "akundefault": "string"
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

### update role

Request :

- Method : PUT
- Endpoint : `/api/v1/akses/petugas/:id`
- Body :

```json
{
  "roleid": "string"
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

### update status petugas

- Method : PUT
- Endpoint : `/api/v1/akses/petugas/status/:id`
- Header : null
- Body :

```json
{
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

### create petugas

Request

- Method : POST
- Endpoint : `/api/v1/akses/petugas`
- Header : null
- Body :

```json
{
  "id": "string",
  "nama": "string",
  "role": "string",
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
{ "data":null,
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

# MENGISI SOAL
## getSoal by bab
Request :

- Method : get
- Endpoint : `/api/v1/mengisiSoal/bab/soal?idbab={idbab}&keyword={}&query`,
- Header : null

Response :

```json
{
    "data":[{
        "id": "Int",
        "idsumber": "Int",
        "idvideo": "Int", 
        "idwacana": "Int",
        "isverif": "Bolean",
        "judulvideo": "String",
        "judulwacana": "String",
        "levelkognitif": "String",
        "metodepengambilan": "String",
        "namapembuat": "String",
        "namasumber": "String",
        "namaverif": "String",
        "nikpembuat": "String",
        "nikverif":"String",
        "opsi": "Json Object",
        "saranpenggunaan": "String",
        "soal": "String HTML",
        "tanggalpembuatan": "String, date",
        "tanggalverif":"String, date",
        "tingkatkesulitan": "int",
        "tipesoal":"String, enum",
        "totalbab": "Int",
        "wacana": "String, HTML",
        "waktupengerjaan": "String Time"//contoh "< 1,5 mnt"
    }],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## getSoal by id
Request :

- Method : get
- Endpoint : `/api/v1/mengisiSoal/bab/soal/{idsoal}`,
- Header : null

Response :

```json
{
    "data":{
        "id": "Int",
        "idsumber": "Int",
        "idvideo": "Int", 
        "idwacana": "Int",
        "isverif": "Bolean",
        "judulvideo": "String",
        "judulwacana": "String",
        "levelkognitif": "String",
        "metodepengambilan": "String",
        "namapembuat": "String",
        "namasumber": "String",
        "namaverif": "String",
        "nikpembuat": "String",
        "nikverif":"String",
        "opsi": "Json Object",
        "saranpenggunaan": "String",
        "soal": "String HTML",
        "tanggalpembuatan": "String, date",
        "tanggalverif":"String, date",
        "tingkatkesulitan": "int",
        "tipesoal":"String, enum",
        "totalbab": "Int",
        "wacana": "String, HTML",
        "waktupengerjaan": "String Time"//contoh "< 1,5 mnt"
    },
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Create Soal By id soal

Request :

- Method : POST
- Endpoint : `/api/v1/mengisiSoal/bab/soal`,
- Header : null
- body:

```json 
        {
        "idsumber": "Int",
        "idvideo": "Int", 
        "idwacana": "Int",
        "isverif": "Bolean",
        "judulvideo": "String",
        "judulwacana": "String",
        "levelkognitif": "String",
        "metodepengambilan": "String",
        "namapembuat": "String",
        "namasumber": "String",
        "namaverif": "String",
        "nikpembuat": "String",
        "nikverif":"String",
        "opsi": "Json Object",
        "saranpenggunaan": "String",
        "soal": "String HTML",
        "tanggalpembuatan": "String, date",
        "tanggalverif":"String, date",
        "tingkatkesulitan": "int",
        "tipesoal":"String, enum",
        "totalbab": "Int",
        "wacana": "String, HTML",
        "waktupengerjaan": "String Time"//contoh "< 1,5 mnt"
    }
```

Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## edit Soal By id soal

Request :

- Method : PUT
- Endpoint : `/api/v1/mengisiSoal/bab/soal/{idSoal}`,
- Header : null
- body:

```json 
        {
        "id": "Int",
        "idsumber": "Int",
        "idvideo": "Int", 
        "idwacana": "Int",
        "isverif": "Bolean",
        "judulvideo": "String",
        "judulwacana": "String",
        "levelkognitif": "String",
        "metodepengambilan": "String",
        "namapembuat": "String",
        "namasumber": "String",
        "namaverif": "String",
        "nikpembuat": "String",
        "nikverif":"String",
        "opsi": "Json Object",
        "saranpenggunaan": "String",
        "soal": "String HTML",
        "tanggalpembuatan": "String, date",
        "tanggalverif":"String, date",
        "tingkatkesulitan": "int",
        "tipesoal":"String, enum",
        "totalbab": "Int",
        "wacana": "String, HTML",
        "waktupengerjaan": "String Time"//contoh "< 1,5 mnt"
    }
```

Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


## Delete Soal By id soal

Request :

- Method : DELETE
- Endpoint : `/api/v1/mengisiSoal/bab/soal/{idsoal}`,
- Header : null
- body:null

Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### verifikasi 

#### Get List Mata Pelajaran

Request :

- Method : GET
- Endpoint : `/api/v1/list/matapelajaran?search=${nama}`

Response :

```json
{
  "id": "number",
  "nama": "string",
  "singkatan": "string",
  "status": "string",
  "issubtk": "string"
}
```

#### Get List Bab

Request :

- Method : GET
- Endpoint : `/api/v1/list/bab/:idmatapelajaran?search=${nama}`
- Header : null
- Body :

```json
{
  "id": "number"
}
```

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "nama": "string",
      "pelajaranbab": "string",
      "upline": "string",
      "total": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### Get List Tree Bab

Request :

- Method : GET
- Endpoint : `api/v1/master/bab/treebab?bab=${id}`

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "kode": "string, unique",
      "nama": "string",
      "namabab": "string",
      "upline": "string",
      "jumlahsoal": "number",
      "peluang": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### Get List Soal

Request :

- Method : GET
- Endpoint : `api/v1/soal/soal?idbab=${id}`

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "tipesoal": "string",
      "levelkognitif": "string",
      "saranpenggunaan": "string",
      "tingkatkesulitan": "string",
      "metodepengambilan": "string",
      "waktupengerjaan": "string",
      "idsumber": "string",
      "namasumber": "string",
      "idvideo": "number",
      "judulvideo": "string",
      "idwacana": "number",
      "judulwacana": "string",
      "totalbab": "number",
      "nikpembuat": "number",
      "namapembuat": "string",
      "tanggalpembuatan": "date",
      "isverif": "string",
      "nikverif": "number | string",
      "namaverif": "string",
      "tanggalverif": "date",
      "soal": "string",
      "opsi": "string",
      "wacana": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```



# Target Pengerjaan Soal

## getTarget by tahun ajaran dan Tingkat Sekolah Kelas
Request :

- Method : get
- Endpoint : `/api/v1/targetPengerjaan?tingkatKelas={tingkatKelas}&&tahunAjaran={tahunAjaran}`,
- Header : null

Response :

```json
    {
    "data":[
        {
        "idmatapelajaran": "int",
        "idtarget": "int",
        "idtingkatkelas": "int",
        "jumlahtarget": "int",
        "namamatapelajaran": "String",
        "tahunajaran": "String",
        "tglakhir": "String, date",
        "tglawal": "String, date"
        }
    ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


## getTarget by id
Request :

- Method : get
- Endpoint : `/api/v1/targetPengerjaan/{idTarget}`,
- Header : null

Response :

```json
    {
    "data":
        {
        "idmatapelajaran": "int",
        "idtarget": "int",
        "idtingkatkelas": "int",
        "jumlahtarget": "int",
        "namamatapelajaran": "String",
        "tahunajaran": "String",
        "tglakhir": "String, date",
        "tglawal": "String, date"
        }
    ,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## create Target Pengerjaan
Request :

- Method : POST
- Endpoint : `/api/v1/targetPengerjaan`,
- Header : 
- body :
```json
{
        "idtingkatkelas": "int",
        "jumlahtarget": "int",
        "idmatapelajaran": "int",
        "tahunajaran": "String",
        "tglakhir": "String, date",
        "tglawal": "String, date"
        }
    
```


Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Edit Target Pengerjaan
Request :

- Method : PUT
- Endpoint : `/api/v1/targetPengerjaan`,
- Header : 
- body :
```json
{       "idtarget":"int",
        "idtingkatkelas": "int",
        "jumlahtarget": "int",
        "idmatapelajaran": "int",
        "tahunajaran": "String",
        "tglakhir": "String, date",
        "tglawal": "String, date"
        }
    
```


Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


## Delete Target Pengerjaan
Request :

- Method : Delete
- Endpoint : `/api/v1/targetPengerjaan/{idTarget}`,
- Header : null


Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


# Paket dan Bundel Soal

## bundel soal

## get list bundel soal
Request :

- Method : GET
- Endpoint : `/api/v1/paketbundel/bundelsoal?tahunajaran={tahunAjaran}&tingkatkelas={tingkatkelas}&peruntukan={prtuntukan}&kelompokujian={kelompokUjian}`,
- Header : null


Response :

```json
{
    "data":[
      

        {
            "deskripsi": "String",
            "id": "int",
            "idkelompokujian": "int",
            "idtingkatkelas": "int",
            "jumlahentri": "int",
            "jumlahsoal": "int",
            "kode": "String",
            "namakelompokujian": "String",
            "opsiurut": "String",
            "peruntukan": "int",
            "status": "String",
            "tahunajaran": "String",
            "tingkatkelas": "String",
            "waktupengerjaan": "int"
        }
    ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## get bundel soal by id
Request :

- Method : GET
- Endpoint : `/api/v1/paketbundel/bundelsoal/{id}`,
- Header : null


Response :

```json
{
    "data":
        {
            "deskripsi": "String",
            "id": "int",
            "idkelompokujian": "int",
            "idtingkatkelas": "int",
            "jumlahentri": "int",
            "jumlahsoal": "int",
            "kode": "String",
            "namakelompokujian": "String",
            "opsiurut": "String",
            "peruntukan": "int",
            "status": "String",
            "tahunajaran": "String",
            "tingkatkelas": "String",
            "waktupengerjaan": "int"
        },
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Create bundel soal
Request :

- Method : POST
- Endpoint : `/api/v1/paketbundel/bundelsoal`,
- Header : null
- body :

```json
      

        {
            "deskripsi": "String",
            "idkelompokujian": "int",
            "idtingkatkelas": "int",
            "jumlahentri": "int",
            "jumlahsoal": "int",
            "kode": "String",
            "opsiurut": "String",
            "peruntukan": "int",
            "tahunajaran": "String",
            "tingkatkelas": "String",
            "waktupengerjaan": "int"
        }
  
```

Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Update bundel soal
Request :

- Method : PUT
- Endpoint : `/api/v1/paketbundel/bundelsoal/{idbundel}`,
- Header : null
- body :

```json
      

        {
            "id":"int",
            "deskripsi": "String",
            "idkelompokujian": "int",
            "idtingkatkelas": "int",
            "jumlahentri": "int",
            "jumlahsoal": "int",
            "kode": "String",
            "opsiurut": "String",
            "peruntukan": "int",
            "tahunajaran": "String",
            "tingkatkelas": "String",
            "waktupengerjaan": "int"
        }
  
```

Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Delete bundel soal
Request :

- Method : Delete
- Endpoint : `/api/v1/paketbundel/bundelsoal/{idbundel}`,
- Header : null
- body :

Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
# Paket Soal   

## get List Paket soal 
Request :

- Method : GET
- Endpoint : `/api/v1/paketbundel/paketsoal?tahunajaran={tahunajaran}&idtingkatkelas={idtingkatkelas}&jenisproduk={idjenisproduk}`,
- Header : null
- body :

Response :

```json
{
    "data":[
         {
            "kode": "String",
            "deskripsi": "String",
            "tahunajaran": "String",
            "tglawal": "String, Date",
            "tglakhir": "String, Date",
            "idjenisproduk": "int",
            "jenisproduk": "String",
            "idtingkatkelas": "int",
            "tingkatkelas": "String",
            "isblockingtime": "Bolean",
            "israndom": "Bolean",
            "status": "String/bolean"//existing "aktif"
        },
    ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## get Paket soal by id Paket
Request :

- Method : GET
- Endpoint : `/api/v1/paketbundel/paketsoal/{id}`,
- Header : null
- body :

Response :

```json
{
    "data":[
         {
            "kode": "String",
            "deskripsi": "String",
            "tahunajaran": "String",
            "tglawal": "String, Date",
            "tglakhir": "String, Date",
            "idjenisproduk": "int",
            "jenisproduk": "String",
            "idtingkatkelas": "int",
            "tingkatkelas": "String",
            "isblockingtime": "Bolean",
            "israndom": "Bolean",
            "status": "String/bolean"//existing "aktif"
        },
    ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Create Paket soal 
Request :

- Method : POST
- Endpoint : `/api/v1/paketbundel/paketsoal`,
- Header : null
- body :
```json
{
  "deskripsi": "String",
  "idtingkatkelas": "int",
  "isblockingtime": "bolean",
  "israndom": "bolean",
  "jenispaket": "int",
  "tahunajaran": "String",
  "tglakhir": "String,date",
  "tglawal": "String,date"
}
```

Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


## Edit Paket soal 
Request :

- Method : PUT
- Endpoint : `/api/v1/paketbundel/paketsoal/{idPaket}`,
- Header : null
- body :
```json
{
  "kodepaket": "String",
  "deskripsi": "String",
  "idtingkatkelas": "int",
  "isblockingtime": "bolean",
  "israndom": "bolean",
  "jenispaket": "int",
  "tahunajaran": "String",
  "tglakhir": "String,date",
  "tglawal": "String,date",
  
}
```

Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


## Delete Paket soal 
Request :

- Method : Delete
- Endpoint : `/api/v1/paketbundel/paketsoal/{idPaket}`,
- Header : null
- body :


Response :

```json
{
    "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


# BUKU

## Buku Teori

## Get List Bab
Request :

- Method : GET
- Endpoint : `/api/v1/Buku-teori/getbab?idmatapelajaran={idMatapelajaran}&namabab={namaBab}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
        "idbab": "int", // permintaan mas agim menambah id
        "kodebab": "String",
        "namabab":"String",
        "upline": "String",
        "jmlteori": "int"
     },
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


## Get List buku teori by kode bab
Request :

- Method : GET
- Endpoint : `/api/v1/Buku-teori/getbab/{idbab}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
  "id": "int",
  "kodebab": "String",
  "namabab": "String,",
  "uraian": "String, HTML",
  "level": "String,",
  "kelengkapan": "String",
  "jmlvideo": "int"
}

  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## create isi bab buku teori
Request :

- Method : POST
- Endpoint : `/api/v1/Buku-teori/getbab`,
- Header : null
- Body : 
```json
{
  "kelengkapan": "Rumus",
  "namaBab": "String",
  "level": "String",
  "uraian": "String, HTML"
}

```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Edit isi bab buku teori
Request :

- Method : PUT
- Endpoint : `/api/v1/Buku-teori/getbab/{id}`,
- Header : null
- Body : 
```json
{
  "kelengkapan": "Rumus",
  "namaBab": "String",
  "level": "String",
  "uraian": "String, HTML"
}

```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Delete isi bab buku teori
Request :

- Method : Delete
- Endpoint : `/api/v1/Buku-teori/getbab/{id}`,
- Header : null
- Body : 
```json
{
  "kelengkapan": "Rumus",
  "namaBab": "String",
  "level": "String",
  "uraian": "String, HTML"
}

```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
# Membuat BUKU

## Get list BUKU
Request :

- Method : Get
- Endpoint : `/api/v1/buku?tahunajaran={value}&kurikulum={value}&tingkatkelas={value}&jenis={value}&semester={value}`
- Header : null
- Body : 


Response :

```json
{
  "data":[
    {
        "deskripsi": "String",
        "idkelompokujian": "int",
        "idkurikulum": "int",
        "idtingkatkelas":"int",
        "jenis":  "String",
        "kelompokujian":  "String",
        "kode": "int",
        "kurikulum":  "String",
        "level":  "String",
        "nama":  "String",
        "semester": "int",
        "tahunajaran": "String",
        "tingkatkelas":  "String"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## create Buku
Request :

- Method : Post
- Endpoint : `/api/v1/buku`
- Header : null
- Body : 
```json
{
  "deskripsi":"String",
  "jenis": "String",
  "kelompokujian": "int",
  "kodebuku": "int",
  "kurikulum": "int",
  "namabuku":"String",
  "semester": "int",
  "tahunajaran": "String", 
  "tingkatkelas": "int"
}

```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Edit Buku
Request :

- Method : PUT
- Endpoint : `/api/v1/buku/{kodebuku}`
- Header : null
- Body : 
```json
{
  "deskripsi":"String",
  "jenis": "String",
  "kelompokujian": "int",
  "kodebuku": "int",
  "kurikulum": "int",
  "namabuku":"String",
  "semester": "int",
  "tahunajaran": "String",
  "tingkatkelas": "int"
}

```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Delete Buku
Request :

- Method : delete
- Endpoint : `/api/v1/buku/{kodebuku}`
- Header : null
- Body :

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
# isi Buku

## Get Isi Buku
Request :

- Method : Get
- Endpoint : `/api/v1/buku/isibuku?kodebuku={kodeBuku}`
- Header : null
- Body : 


Response :

```json
{
  "data":[
         {
            "idisibuku": "int",
            "kodebuku": "int",
            "kodebab": "String",
            "namabab": "String",
            "upline": "String"
        },
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## set Isi Buku
Request :

- Method : PUT
- Endpoint : `/api/v1/buku/isibuku`
- Header : null
- Body : 
```json
{
    "babs": ["int,String"],//list of kodebab/idbab
    "kodebuku": "int"
}
```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


# produk BUKU
## Get Produk Buku
Request :

- Method : Get
- Endpoint : `/api/v1/buku/produkbuku?kodebuku={kodebuku}`
- Header : null
- Body : 


Response :

```json
{
  "data":[
        {
            "kode": "int",
            "idproduk":  "int",
            "namaproduk": "String"
        },
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Tambah Produk Buku
Request :

- Method : PUT
- Endpoint : `/api/v1/buku/produkbuku`
- Header : null
- Body : 

```json
{
    "kodeBuku": "int",
    "porduks":["int"]//list id Produk
}
```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Delete Produk Buku
Request :

- Method : Delete
- Endpoint : `/api/v1/buku/produkbuku/{kodeBuku}`
- Header : null
- Body : 


Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


# Buku Teaser

## list Buku Teaser
Request :

- Method : Get
- Endpoint : `/api/v1/buku/bukuteoriteaser?tingkatkelas={value}`
- Header : null
- Body : 


Response :

```json
{
  "data":[
        {
            "idtingkatkelas": "int",
            "role": "String",
            "tglawal": "String,date",
            "tglakhir": "String,date",
            "tahunajaran": "String",
            "idkurikulum": "int",
            "semester": "int",
            "jenis": "String",
            "kodebuku": "int",
            "namabuku": "String"
        },

  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Tambah Buku Teaser
Request :

- Method : POST
- Endpoint : `/api/v1/buku/bukuteoriteaser/`
- Header : null
- Body : 
```json
{
    "tingkatkelas":"int",
    "role":"String",
    "tglawal":"String,date",
    "tglakhir":"String,date",
    "kodebuku":"int"
}

```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Edit Buku Teaser
Request :

- Method : Put
- Endpoint : `/api/v1/buku/bukuteoriteaser/{kodebuku}`
- Header : null
- Body : 
```json
{
    "tingkatkelas":"int",
    "role":"String",
    "tglawal":"String,date",
    "tglakhir":"String,date",
    "kodebuku":"int"
}

```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Delete Buku Teaser
Request :

- Method : Delete
- Endpoint : `/api/v1/buku/bukuteoriteaser/{kodebuku}`
- Header : null
- Body : 


Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

 ## get List nama BUKU 
 ### untuk Mengambil kode buku saat menambahkan di teaser
 Request :

- Method : Get
- Endpoint : `/api/v1/list/namabuku?tingkatkelas={value}&tahunajaran={value}&kurikulum={value}&semester={value}&jenis={value}`
- Header : null
- Body : 


Response :

```json
{
  "data":[
     {
            "kode": "int",
            "nama": "String"
        },
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## BAH

### Membuat BAH

#### Get DataTabel BAH

Request :

- Method : GET
- Endpoint : `/api/v1/bah/datatabel?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?kurikulum={value}?tingkat_kelas={value}?jenislayanan={value}?kelompok_ujian={value}?`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "id": "unique",
            "kode_bah": "string, unique",
            "semester": "number",
            "tahunajaran": "string",
            "jumlahpertemuan": "number",
            "idjenislayanan": "unique",
            "jenislayanan": "string",
            "idkurikulum": "unique",
            "kurikulum": "string",
            "idtingkatkelas": "unique",
            "tingkatkelas": "string",
            "idkelompokujian": "unique",
            "kelompokujian": "string",
            "idsilabus": "unique",
            "namasilabus": "string",
            "created_at": "2023-09-14 09:42:40",
            "updated_at": "2022-06-13 22:12:54"
        },
    ],
    "metadata": {
        "total_count": "number",
        "page_count": "number",
        "page": "number",
        "per_page": "number",
        "sort": "desc",
        "order_by": "created_at",
        "keyword": "string"
    }
}
```

#### Get Bah Bab 

Request :

- Method : GET
- Endpoint : `/api/v1/bah/bah-bab?id_bah={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "pertemuan": "number",
            "kodebab": "string, unique",
            "root": "string, unique",
            "namabab": "string",
            "upline": "number",
            "child": "number"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Get Bah Bab Silabus

Request :

- Method : GET
- Endpoint : `/api/v1/bah/bah-bab/silabus?id_bah={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "pertemuan": "number",
            "kodebab": "string, unique",
            "root": "string, unique",
            "namabab": "string",
            "upline": "number",
            "child": "number"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Get Bab Mapel

Request :

- Method : GET
- Endpoint : `/api/v1/bah/bab?mapel={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "id": "unique",
            "kode_bah": "string, unique",
            "semester": "number",
            "tahunajaran": "string",
            "jumlahpertemuan": "number",
            "idjenislayanan": "unique",
            "jenislayanan": "string",
            "idkurikulum": "unique",
            "kurikulum": "string",
            "idtingkatkelas": "unique",
            "tingkatkelas": "string",
            "idkelompokujian": "unique",
            "kelompokujian": "string",
            "idsilabus": "unique",
            "namasilabus": "string",
            "created_at": "2023-09-14 09:42:40",
            "updated_at": "2022-06-13 22:12:54"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Tambah Bah

Request :

- Method : POST
- Endpoint : `/api/v1/bah`,
- Header : null
- Body : 
```json
{
    "idsilabus": "string, unique",
    "idjenislayanan": "unique",
    "idkurikulum": "unique",
    "idtingkatkelas": "unique",
    "idkelompokujian": "unique",
    "nama": "string",
    "semester": "number",
    "tahunajaran": "2023/2024",
    "jumlahpertemuan": "number",
    "detaildata": [
        {
            "pertemuan": "number",
            "kodebab": "string, unique",
            "root": "string, unique",
            "namabab": "string",
            "upline": "number",
            "child": "number"
        },
    ],
}
```

Response :

```json
{
  "data": [
        {
            "idsilabus": "string, unique",
            "idjenislayanan": "unique",
            "idkurikulum": "unique",
            "idtingkatkelas": "unique",
            "idkelompokujian": "unique",
            "nama": "string",
            "semester": "number",
            "tahunajaran": "2023/2024",
            "jumlahpertemuan": "number",
            "detaildata": [
                {
                    "pertemuan": "number",
                    "kodebab": "string, unique",
                    "root": "string, unique",
                    "namabab": "string",
                    "upline": "number",
                    "child": "number"
                },
            ],
        }
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Update Bah

Request :

- Method : PUT
- Endpoint : `/api/v1/bah/{id_bah}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "idsilabus": "string, unique",
            "idjenislayanan": "unique",
            "idkurikulum": "unique",
            "idtingkatkelas": "unique",
            "idkelompokujian": "unique",
            "nama": "string",
            "semester": "number",
            "tahunajaran": "2023/2024",
            "jumlahpertemuan": "number",
            "detaildata": [
                {
                    "pertemuan": "number",
                    "kodebab": "string, unique",
                    "root": "string, unique",
                    "namabab": "string",
                    "upline": "number",
                    "child": "number"
                },
            ],
        }
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Delete Bah

Request :

- Method : DELETE
- Endpoint : `/api/v1/bah/{id_bah}`,
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

### Menautkan BAH

#### Get DataTabel BAH Pemasangan

Request :

- Method : GET
- Endpoint : `/api/v1/bah/datatabel/list-pemasangan?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?semester={value}?tingkat_kelas={value}?kelas={value}?kelompok_ujian={value}?`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "id": "unique",
            "kode_bah": "string",
            "semester": "number",
            "tahunajaran": "string",
            "jumlahpertemuan": "number",
            "idjenislayanan": "unique",
            "jenislayanan": "string",
            "idkurikulum": "unique",
            "kurikulum": "string",
            "idtingkatkelas": "unique",
            "tingkatkelas": "string",
            "idkelompokujian": "unique",
            "kelompokujian": "string",
            "created_at": "2023-09-14 09:42:40",
            "updated_at": "2022-06-13 22:12:54"
        },
    ],
    "metadata": {
        "total_count": "number",
        "page_count": "number",
        "page": "number",
        "per_page": "number",
        "sort": "desc",
        "order_by": "created_at",
        "keyword": "string"
    }
}
```

#### Get BAH Kelas

Request :

- Method : GET
- Endpoint : `/api/v1/bah/bah-kelas?tahun_ajaran={value}?semester={value}?tingkat_kelas={value}?kelas={value}?kelompok_ujian={value}?kurikulum={value}?jml_pertemuan={value}?id_jenis_layanan={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "id": "unique",
            "kode": "string",
            "idkurikulum": "unique",
            "kurikulum": "string",
            "idjenislayanan": "unique",
            "jenislayanan": "string",
            "jumlahpertemuan": "number",
            "cek": "number",
            "created_at": "2023-09-14 09:42:40",
            "updated_at": "2022-06-13 22:12:54"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Tambah Pemasangan BAH Kelas

Request :

- Method : POST
- Endpoint : `/api/v1/bah/bah-kelas`,
- Header : null
- Body : 

```json
{
  "kelas": "270286",
  "idbahs": [
    9010
  ],
  "allidbahs": [
    9010
  ]
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

#### Delete Pemasangan BAH Kelas

Request :

- Method : DELETE
- Endpoint : `/api/v1/bah/bah-kelas?kelas={value}?id_bah={value}`,
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


### Monitoring BAH

#### Get DataTabel Monitoring BAH Kelas

Request :

- Method : GET
- Endpoint : `/api/v1/bah/datatabel/list-monitoring?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?gedung={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "id_kelas": "unique",
            "nama_kelas": "string",
            "tingkat_kelas": "string",
            "jenis_kelas": "REGULER",
            "jumlah_bah": "number",
            "status_bah": "13 BAH TERTAUT",
            "created_at": "2023-09-14 09:42:40",
            "updated_at": "2022-06-13 22:12:54"
        },
    ],
    "metadata": {
        "total_count": "number",
        "page_count": "number",
        "page": "number",
        "per_page": "number",
        "sort": "desc",
        "order_by": "created_at",
        "keyword": "string"
    }
}
```


#### Get DataTabel Monitoring BAH Kelas Detail

Request :

- Method : GET
- Endpoint : `/api/v1/bah/datatabel/list-monitoring/detail?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?id_kelas={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "id": "unique",
            "kode": "24.12.15.32.11.14-0001",
            "semester": "number",
            "tahunajaran": "string",
            "jumlahpertemuan": "number",
            "idjenislayanan": "unique",
            "jenislayanan": "string",
            "idkurikulum": "unique",
            "kurikulum": "string",
            "idtingkatkelas": "unique",
            "tingkatkelas": "string",
            "idkelompokujian": "unique",
            "kelompokujian": "string",
            "created_at": "2023-09-14 09:42:40",
            "updated_at": "2022-06-13 22:12:54"
        },
    ],
    "metadata": {
        "total_count": "number",
        "page_count": "number",
        "page": "number",
        "per_page": "number",
        "sort": "desc",
        "order_by": "created_at",
        "keyword": "string"
    }
}
```


## TOB

### MEMBUAT TOB

#### GET JENIS TOB

Request :

Method : GET
Endpoint : `/api/v1/jenisTob`,
Header : null
Body : null

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "name": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

<!-- ### GET JENIS PRODUK

Request :

Method : GET
Endpoint : `/api/v1/jenisProduk`,
Header : null
Body : null

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "name": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
``` -->

#### TAMBAH TOB

Request :

Method : POST
Endpoint : `/api/v1/tob`,
Header : null
Body :

```json
{
  "tahunAjaran": "string",
  "formatMerdeka": "boolean",
  "namaTob": "string",
  "jarakAntarPaket": "number",
  "tanggalAwal": "date and time",
  "tanggalAkhir": "date and time",
  "jenisTob": "string"
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

#### GET DATA TABLE LIST TOB

Request :

Method : GET
Endpoint : `/api/v1/tob/${params.tahunAjaran}/${params.jenisTob}`,
Header : null
Body : null

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "kode": "number",
      "nama": "string",
      "jenistob": "string",
      "jarakantarpaket": "string",
      "tglawal": "date and time",
      "tglakhir": "date and time",
      "tahunajaran": "2022/2023",
      "istomerdeka": 0,
      "status": "Aktif"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

#### GET DETAIL TOB

Request :

Method : GET
Endpoint : `/api/v1/tob/${params.kodeTob}`,
Header : null
Body : null

Response :

```json
{
  "data": {
    "id": "string, unique",
    "kode": "string",
    "deskripsi": "string",
    "tglawal": "date and time",
    "tglakhir": "date and time",
    "isblockingtime": "number",
    "israndom": "number",
    "iswajib": "number",
    "urut": "number"
  },
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### UBAH TOB

Request :

Method : PUT
Endpoint : `/api/v1/tob`,
Header : null
Body :

```json
{
  "tahunAjaran": "string",
  "formatMerdeka": "boolean",
  "namaTob": "string",
  "jarakAntarPaket": "number",
  "tanggalAwal": "date and time",
  "tanggalAkhir": "date and time",
  "jenisTob": "string"
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

#### TAMBAH PAKET SOAL

Request :

Method : PUT
Endpoint : `/api/v1/tob/paket-soal`,
Header : null
Body :

```json
{
  "kodetob": "number",
  "kodepaket": "array",
  "allkodepaket": "array"
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

#### GET PRODUK TOB

Request :

Method : GET
Endpoint : `/api/v1/tob/produk-tob/${param.kodeTob}`,
Header : null
Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "kode": "number",
      "idproduk": "number",
      "namaproduk": "String"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### GET SYARAT EMPATI

Request :

Method : GET
Endpoint : `/api/v1/tob/syarat-empati/${param.kodeTob}`,
Header : null
Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "namTO": "String",
      "syarat": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### GET OPTION SYARAT EMPATI

Request :

Method : GET
Endpoint : `/api/v1/tob/to-empati/${param.tahunAjaran}/${param.tanggalAwal}/${param.tanggalAkhir}`,
Header : null
Body : null

Response :

```json
{
  "data": [
    {
      "id": "string",
      "namaproduk": "String"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### TAMBAH KOMPONEN PRODUK

Request :

Method : PUT
Endpoint : `/api/v1/tob/komponen-produk`,
Header : null
Body :

```json
{
  "kodetob": "number",
  "kodepaket": "array",
  "allkodepaket": "array"
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

### PAKET SOAL TEASER

#### TAMBAH DATA PAKET SOAL TEASER

Request :

Method : POST
Endpoint : `/api/v1/tob/paket-soal-teaser`,
Header : null
Body :

```json
{
  "tingkatKelas": "string",
  "role": "string",
  "tanggalAwal": "date and time",
  "tanggalAkhir": "date and time",
  "tahunAjaran": "string",
  "namaTob": "string"
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

#### UBAH DATA PAKET SOAL TEASER

Request :

Method : PUT
Endpoint : `/api/v1/tob/paket-soal-teaser`,
Header : null
Body :

```json
{
  "tingkatKelas": "string",
  "role": "string",
  "tanggalAwal": "date and time",
  "tanggalAkhir": "date and time",
  "tahunAjaran": "string",
  "namaTob": "string"
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

#### DELETE DATA PAKET SOAL TEASER

Request :

Method : DELETE
Endpoint : `/api/v1/tob/paket-soal-teaser/${params.idPaketSoalTeaser}`,
Header : null
Body : null

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

#### GET DATA TABLE LISTS PAKET SOAL TEASER

Request :

Method : GET
Endpoint : `/api/v1/tob/paket-soal-teaser`,
Header : null
Body : null

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "idtingkatkelas": "number",
      "role": "string",
      "tglawal": "date and time",
      "tglakhir": "date and time",
      "tahunajaran": "string",
      "kodetob": "number",
      "namatob": "string",
      "idproduk": "number",
      "jmlproduk": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```


## VIDEO TEASER

### TAMBAH DATA VIDEO TEASER

Request :

- Method : POST
- Endpoint : `/api/v1/video-teaser`
- Header : null
- Body :

```json
{
  "tingkatKelas": "string",
  "role": "string",
  "tanggalAwal": "string",
  "tanggalAkhir": "string",
  "linkVideo": "string",
  "namaVideo": "string"
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

### GET DATA TABLE LIST VIDEO TEASER

Request :

- Method : GET
- Endpoint : `/api/v1/video-teaser/${params.tingkatKelas}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "idtingkatkelas": "number",
      "role": "string",
      "tglawal": "date and time",
      "tglakhir": "date and time",
      "linkvideo": "string",
      "namaVideo": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

### UBAH VIDEO TEASER

Request :

- Method : PUT
- Endpoint : `/api/v1/video-teaser`
- Header : null
- Body :

```json
{
  "tingkatKelas": "string",
  "role": "string",
  "tanggalAwal": "string",
  "tanggalAkhir": "string",
  "linkVideo": "string",
  "namaVideo": "string"
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

### DELETE DATA VIDEO TEASER

Request :

- Method : DELETE
- Endpoint : `/api/v1/video-teaser/${params.idVideo}`
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

## VIDEO EKSTRA

### TAMBAH DATA VIDEO EKSTRA

Request :

- Method : POST
- Endpoint : `/api/v1/video-teaser`
- Header : null
- Body :

```json
{
  "tingkatKelas": "string",
  "tahunAjarang": "string",
  "jenisLayanan": "string",
  "role": "string",
  "tanggalAwal": "string",
  "tanggalAkhir": "string",
  "linkVideo": "string",
  "namaVideo": "string",
  "mataPelajaran": "string",
  "bab": "string"
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

### UBAH VIDEO EKSTRA

Request :

- Method : PUT
- Endpoint : `/api/v1/video-ekstra`
- Header : null
- Body :

```json
{
  "tingkatKelas": "string",
  "tahunAjarang": "string",
  "jenisLayanan": "string",
  "role": "string",
  "tanggalAwal": "string",
  "tanggalAkhir": "string",
  "linkVideo": "string",
  "namaVideo": "string",
  "mataPelajaran": "string",
  "bab": "string"
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

### GET DATA TABLE LIST VIDEO EKSTRA

Request :

- Method : GET
- Endpoint : `/api/v1/video-ekstra/${params.tingkatKelas}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "idtingkatkelas": "number",
      "tingkatkelas": "number",
      "tahunajaran": "string",
      "layanan": "number",
      "jenislayanan": "string",
      "idvideo": "number",
      "namavideo": "string",
      "role": "string",
      "jenisvideo": "string",
      "idkomponenproduk": "number",
      "komponenproduk": "string",
      "tglawal": "date and time",
      "tglakhir": "date and time",
      "linkvideo": "string",
      "header": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

### DELETE DATA VIDEO EKSTRA

Request :

- Method : DELETE
- Endpoint : `/api/v1/video-ekstra/${params.idVideo}`
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


## Produk Kelompok

### getAll

Request :

- Method : GET
- Endpoint : `/api/v1/produk-kelompok/get-all?search=${nama_kelompok}&sortby=${nama_kelompok|jumlah_anggota|jumlah_produk|ispengajar}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Header : null

Response :

```json
{
  "data": [
    {
      "id_kelompok": "number, unique",
      "nama_kelompok": "string",
      "jumlah_anggota": "number",
      "jumlah_produk": "number",
      "isPengajar": "boolean",
      "createdAt": "date",
      "updatedAt": "date"
    },
    {},
    {}
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

### getById

Request :

- Method : GET
- Endpoint : `/api/v1/produk-kelompok/get-byid/:id_kelompok?search=${nama_kelompok}&sortby=${nama_produk|jenis_produk|tglawal|tglakhir}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Header : null

Response :

```json
{
  "data": [
    {
      "id_kelompok": "number, unique",
      "nama_produk": "string",
      "jenis_produk": "string",
      "tglawal": "date",
      "tglakhir": "date"
    },
    {},
    {}
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

<!-- get untuk nambah produk -->

### getPodukId

Request :

- Method : GET
- Endpoint : `/api/v1/produk-kelompok/get-produk?id=${id}&jenisprodukid=${id}&jenislayanan={id}&cari=${produk}&page=${page}&limit=${limit}`
- Header : null

Response :

```json
{
  "data": [
    {
      "id_produk": "number, unique",
      "nama_produk": "string",
      "id_nama_produk": "string",
      "tglawal": "date",
      "tglakhir": "date",
      "cek": "boolean"
    },
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

### post produk

Request :

- Method : POST
- Endpoint : `/api/v1/produk-kelompok/produkpengajar/:idkelompok`
- Header : null
- Body (ArrayObj || Obj) :

```json
{
  "idProduk": "number, req",
  "startDate": "date, req",
  "endDate": "date, req"
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


## JPMP

### JPMP

## Get List JPMP
Request :

- Method : Get
- Endpoint : `/api/v1/jpmp?tingkatkelas={value}&tahunajaran={value}&semester={value}`
- Header : null
- Body : 


Response :

```json
{
  "data":[
     {
            "c_IdJuklak": "int",
            "c_IdSekolahKelas": "int",
            "c_Semester": "int",
            "c_TahunAjaran": "String",
            "c_JenisLayanan": "String",
            "c_NamaJuklak": "String",
            "c_HariBelajar": "String",
            "c_JumlahPertemuanPerMinggu": "int",
            "c_TanggalAwal": "String, date",
            "c_TanggalAkhir": "String, date",
            "c_TotalPertemuan": "int",
            "c_DetailTotalPertemuan":"String HTML" ,
            //contoh "{\"PENGARAHAN\": 2, \"TOTAL KBM KODING\": 111, \"GOA (DI LUAR KBM)\": 0, \"TOBK (DI LUAR KBM)\": 8, \"RESPONSI DI LUAR KBM\": 0, \"KAPITA SELEKTA THE KING\": 4}",
            "c_LastUpdate": "String, datetime",
            "c_KodeJuklak": "String",
            "c_Updater": "String",
            "c_TanggalUpload":"String,datetime",
            "c_Uploader": "String",
            "c_Status": "bolean",
            "c_JmlDet": "int"
        },
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Get Detail JPMP
Request :

- Method : Get
- Endpoint : `/api/v1/jpmp/{kodejuklak}`
- Header : null
- Body : 


Response :

```json
{
  "data":[
             {
                "c_TanggalAwal": "String, date",
                "c_TanggalAkhir": "String, date",
                "c_MataPelajaran":[
                    {
                        "idmatapelajaran": "int",
                        "namamatapelajaran": "String",
                        "JumlahPembelajaran":"int"
                    }
                ],
                "c_Status": "String",
                "c_TanggalUpload": "String, datetime",
            },,
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Download Tamplate JPMP
Request :

- Method : Get
- Endpoint : `/api/v1/jpmp/tamplate/jpmp`
- Header : null
- Body : 


Response :

```json
{
  "data":"file Tamplate JPMP",
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Download Tamplate JPMP Detail
Request :

- Method : Get
- Endpoint : `/api/v1/jpmp/tamplate/jpmpdetail`
- Header : null
- Body : 


Response :

```json
{
  "data":"file Tamplate JPMP Detail",
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## upload Tamplate JPMP 
Request :

- Method : POST
- Endpoint : `/api/v1/jpmp/tamplate/jpmp`
- Header : null
- Body : 

```json
{
  "file":"file tamplate",

}
```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## upload Tamplate JPMP Detail 
Request :

- Method : POST
- Endpoint : `/api/v1/jpmp/tamplate/jpmpdetail`
- Header : null
- Body : 

```json
{
  "file":"file tamplate",

}
```

Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Set Aktif/tidak di JPMP 
Request :

- Method : Get
- Endpoint : `/api/v1/jpmp/{kodejuklak}`
- Header : null
- Body : 
```json
    {
        "kodejuklak":"int",
        "status":"bolean",
        "tanggalawal":"String,date", // jika hanya ingin mengubah detail di salah satu tanggal, kalau semua tidak perluada
    }
```


Response :

```json
{
  "data":null,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```




### JPMP KELAS

## Get Penanda
Request :

- Method : GET
- Endpoint : `/api/v1/penanda?keyword={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
     {
            "id": "int",
            "nama": "String"
        },
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Get Zona
Request :

- Method : GET
- Endpoint : `/api/v1/zona?penanda={idPenanda}&&keyword={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
     {
            "id": "int",
            "nama": "String"
        },
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Get Gedung
Request :

- Method : GET
- Endpoint : `/api/v1//zona?zona={idzona}&&keyword={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
     {
            "id": "int",
            "nama": "String"
        },
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Get JPMP Kelas
Request :

- Method : GET
- Endpoint : `/api/v1/jpmpkelas?gedung={idgedung}&tingkatkelas={tingkatKelas}&tahunajaran={tahunAjaran}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "c_IdKelas": "int",
            "c_NamaKelas": "String",
            "c_TanggalStart": "String, date",
            "c_TanggalBerakhir": "String, date",
            "c_TanggalLaunching": "String, date",
            "c_TanggalRunning": "String, date",
            "c_Status": "String, date",
            "c_HariBelajar": "String, date",
            "c_SingkatanLayanan":"String, date",
            "c_status_validator_kacap":"bolean",
            "c_status_validator_BMP":"bolean",
            "c_Singkatan": "String, date",
            "c_JenisKelas": "String, date",
            "c_Data": "[{\"HB\": \"SELASA(2)-JUM'AT(2)\", \"ID\": 42963, \"NM\": \"11 IPA REGULER 4 Pert K13 REVISI\", \"TP\": \"2023/2024\", \"SMT\": \"1\", \"TOT\": 80, \"AWAL\": \"2023-07-11\", \"JPPM\": 4, \"AKHIR\": \"2023-12-16\", \"DETOT\": {\"KBM KODING\": 73, \"PENGARAHAN\": 2, \"PEMBEKALAN UTBK\": 2, \"GOA (DI LUAR KBM)\": 1, \"TOBK (DI LUAR KBM)\": 12, \"RESPONSI (DI LUAR KBM)\": 0, \"KAPITA SELEKTA THE KING\": 2, \"PEMBAHASAN PEMBEKALAN UTBK\": 1}, \"KEPNG\": null, \"PTACC\": \"\", \"PTPNG\": null, \"STPNG\": \"T\", \"TGACC\": null, \"TGPNG\": null, \"KETERANGAN\": null}]",
            //   [{
//     "HB": "SELASA(2)-JUM'AT(2)",
//     "ID": 42963,
//     "NM": "11 IPA REGULER 4 Pert K13 REVISI",
//     "TP": "2023/2024",
//     "SMT": "1",
//     "TOT": 80,
//     "AWAL": "2023-07-11",
//     "JPPM": 4,
//     "AKHIR": "2023-12-16",
//     "DETOT": {
//       "KBM KODING": 73,
//       "PENGARAHAN": 2,
//       "PEMBEKALAN UTBK": 2,
//       "GOA (DI LUAR KBM)": 1,
//       "TOBK (DI LUAR KBM)": 12,
//       "RESPONSI (DI LUAR KBM)": 0,
//       "KAPITA SELEKTA THE KING": 2,
//       "PEMBAHASAN PEMBEKALAN UTBK": 1
//     },
//     "KEPNG": null,
//     "PTACC": "",
//     "PTPNG": null,
//     "STPNG": "T",
//     "TGACC": null,
//     "TGPNG": null,
//     "KETERANGAN": null
//   }
// ]
        }
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Get List Juklak
Request :

- Method : GET
- Endpoint : `/api/v1/juklak?tahunajaran={value}&tingkatkelas={value}&semester={value}&jenislayanan={value}&status={Value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
         {
            "id": "int",
            "nama": "String",
            "c_NamaJuklak": "String",
            "c_HariBelajar": "String",
            "c_DetailTotalPertemuan": "{\"KBM KODING\": 73, \"PENGARAHAN\": 2, \"PEMBEKALAN UTBK\": 2, \"GOA (DI LUAR KBM)\": 1, \"TOBK (DI LUAR KBM)\": 12, \"RESPONSI (DI LUAR KBM)\": 0, \"KAPITA SELEKTA THE KING\": 2, \"PEMBAHASAN PEMBEKALAN UTBK\": 1}"
            //   contoh kalau di ubah          {
            // "KBM KODING": 73,
            // "PENGARAHAN": 2,
            // "PEMBEKALAN UTBK": 2,
            // "GOA (DI LUAR KBM)": 1,
            // "TOBK (DI LUAR KBM)": 12,
            // "RESPONSI (DI LUAR KBM)": 0,
            // "KAPITA SELEKTA THE KING": 2,
            // "PEMBAHASAN PEMBEKALAN UTBK": 1
            // }

        },
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Buat JPMP Kelas

Request :

- Method : POST
- Endpoint : `/api/v1/jpmpkelas`,
- Header : null
- Body : 
```json
{
  "kelas": "int",
  "semester": "int",
  "kodejuklak": "int"
}
```

Response :

```json
{
  "data": null,

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Delete JPMP Kelas

Request :

- Method : Delete
- Endpoint : `/api/v1/jpmpkelas/{kodeJuklakKelas}`,
- Header : null
- Body : 


Response :

```json
{
  "data": null,

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


## Get Pengajuan

Request :

- Method : GET
- Endpoint : `/api/v1/jpmpkelas/pengajuan?kodejuklak={value}&kelas={value}&semester={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
 
    "startdate": "2023-08-25",
    "enddate": "2023-09-24",
    "Default": [
        {
                "id": "number",
                "nama": "String",
                "Jumlah": "number",
        }  
    ],
      "Pengajuan": [
        {
                "id": "number",
                "nama": "String",
                "Jumlah": "number",
        }  
    ]

        }
  ],

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Update Pengajuan

Request :

- Method : PUT
- Endpoint : `/api/v1/jpmpkelas/pengajuan`,
- Header : null
- Body : 
```json
{
    "kodejuklak":"int",
    "kelas":"int",
    "semester": "int",
    "detail":[
                {
            
                "startdate": "2023-08-25",
                "enddate": "2023-09-24",
                "Default": [
                    {
                            "id": "number",
                            "nama": "String",
                            "Jumlah": "number",
                    }  
                ],
                "Pengajuan": [
                    {
                            "id": "number",
                            "nama": "String",
                            "Jumlah": "number",
                    }  
                ]

                    }
            ]
}
```

Response :

```json
{
  "data": null,

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## validasi JPMP
Request :

- Method : PUT
- Endpoint : `/api/v1/jpmpkelas/validasi`,
- Header : null
- Body : 
```json
{
    "kodejuklak":"int",
    "kelas":"int",
    "semester": "int",
    "isDisetujui":"bolean",
    "user_id": "String"
}
```

Response :

```json
{
  "data": null,

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
