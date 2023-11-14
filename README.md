# API Spec

# MODUL SMBA

## Akses Role

### getAll

Request :

- Method : GET
- Endpoint : `/api/v1/akses/roles/get-all?&sortby=${nama|status|total}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Header : null

Response :

```json
{
  "data": [
    {
      "id": "number, unique",
      "nama": "string",
      "status": "boolean",
      "total": "number"
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

### update role name

- Method : PUT
- Endpoint : `/api/v1/akses/roles`
- Header : null
- Body :

```json
{
  "id": "number",
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

### update status

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

## MASTER

### MATA PELAJARAN

#### TAMBAH MATA PELAJARAN

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

#### EDIT MATA PELAJARAN

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

#### GET LIST MATA PELAJARAN

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

#### GET DETAIL MATA PELAJARAN

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

#### DELETE BY ID MATA PELAJARAN

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

#### TAMBAH KURIKULUM

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

#### EDIT Kurikulum

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

#### GET LIST KURIKULUM

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

#### GET DETAIL KURIKULUM

Request :

- Method : GET
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

#### TAMBAH BAB

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

#### EDIT BAB

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

#### GET LIST BAB

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

#### GET DETAIL BAB

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

#### GET TAHUN AJARAN

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

#### GET TINGKAT KELAS

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

#### GET Layanan/JENIS KELAS

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

#### GET KELOMPOK UJIAN

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

#### TAMBAH SILABUS

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

#### GET LIST SILABUS

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

#### GET DETAIL SILABUS

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

#### TAMBAH MATA AJAR

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

#### EDIT MATA AJAR

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

#### GET LIST MATA AJAR

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

#### GET DETAIL MATA AJAR

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

## SOAL

### SUMBER SOAL

#### GET JENIS SUMBER SOAL

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

#### TAMBAH SUMBER SOAL

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

#### EDIT SUMBER SOAL

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

#### GET LIST SUMBER SOAL

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

#### GET DETAIL ISI KODE SUMBER

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

#### GET LIST WACANA

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

#### GET DETAIL WACANA

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

#### TAMBAH WACANA

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

#### UPDATE WACANA

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

#### HAPUS WACANA

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

### UPLOAD VIDEO

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

### MENGISI SOAL

#### getSoal by bab
Request :

- Method : get
- Endpoint : `/api/v1/mengisiSoal/bab/soal?idbab={idbab}`,
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


#### getSoal by id
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


#### Create Soal By id soal

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

#### edit Soal By id soal

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


#### Delete Soal By id soal

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



### Target Pengerjaan Soal

#### getTarget by tahun ajaran dan Tingkat Sekolah Kelas
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


#### getTarget by id
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

#### create Target Pengerjaan
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

#### Edit Target Pengerjaan
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


#### Edit Target Pengerjaan
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


## Paket dan Bundel Soal

### bundel soal

#### get list bundel soal
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

#### get bundel soal by id
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

#### Create bundel soal
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

#### Update bundel soal
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


#### Delete bundel soal
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

### Paket Soal   

#### get List Paket soal 
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

#### get Paket soal by id Paket
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

#### Create Paket soal 
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


#### Edit Paket soal 
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


#### Delete Paket soal 
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


## BUKU

### Buku Teori

#### Get List Bab
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


#### Get List buku teori by kode bab
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

#### create isi bab buku teori
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

#### Edit isi bab buku teori
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

#### Delete isi bab buku teori
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

### Membuat BUKU

#### Get list BUKU
Request :

- Method : Get
- Endpoint : `/api/v1/buku?tahunajaran={ta}&kurikulum={kurikulum}&tingkatkelas={tk}&jenis={jenis}&semester={smt}`
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

#### create Buku
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

#### Edit Buku
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

#### Delete Buku
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

#### isi Buku

##### Get Isi Buku
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
##### Update Isi Buku
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


### produk BUKU

#### Get Produk Buku
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
##### Tambah Produk Buku
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
#### Delete Produk Buku
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


### Buku Teaser

#### list Buku Teaser
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

#### Tambah Buku Teaser
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


#### Edit Buku Teaser
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


#### Delete Buku Teaser
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

 #### get List nama BUKU 

 // untuk Mengambil kode buku saat menambahkan di teaser

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

#### Get List JPMP
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

#### Get Detail JPMP
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


#### Download Tamplate JPMP
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


#### Download Tamplate JPMP Detail
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

#### upload Tamplate JPMP 
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


#### upload Tamplate JPMP Detail
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

#### Set Aktif/tidak di JPMP 
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

#### Get Penanda
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


#### Get Zona
Request :

- Method : GET
- Endpoint : `/api/v1//zona?penanda={idPenanda}&&keyword={value}`,
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


#### Get Gedung
Request :

- Method : GET
- Endpoint : `/api/v1//zona?penanda={idPenanda}&&keyword={value}`,
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


## Kunci Jawaban

### Jenis Produk

Request :

- Method : GET
- Endpoint : `/api/v1/produk`
- Header : null

Response :

```json
{
  "data": {
    "id": "number, unique",
    "nama_produk": "string",
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

### Kelompok Ujian

Request :

- Method : GET
- Endpoint : `/api/v1/kelompok-ujian`
- Header : null

Response :

```json
{
  "data": {
    "id": "number, unique",
    "nama_kelompok_ujian": "string",
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

### Kode Paket

Request :

- Method : GET
- Endpoint : `/api/v1/kode-paket`
- Header : null

Response :

```json
{
  "data": {
    "id": "number, unique",
    "nama_kode_paket": "string",
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

### Tambah Kunci Jawaban

Request :

- Method : POST
- Endpoint : `/api/v1/kunci-jawaban`
- Header : null
- Body :

```json
{
  "id_jenis_produk": "number",
  "id_kelompok_ujian": "number",
  "id_kode_paket": "number"
}
```

Response :

```json
{
  "data": {
    "id_kunci_jawaban": "number, unique",
    "no_urut": "string | number",
    "id_soal": "string | number",
    "kelompok_ujian": "string",
    "bab": "string | number",
    "kode_sumber": "string | number",
    "tipe_soal": "string | number",
    "level": "string | number",
    "kunci_jawaban": "string | number",
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


# MODUL GO KASIR

## Dashboard

### Dashboard Pusat

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/dashboard`

Response :

```json
{
  "result": true,
  "data": {
    "saldo": {
      "SaldoSetor": "125.300.000",
      "Tunggakan": "245.000.000"
    },
    "jumsis": [
      {
        "Id": "1",
        "Kelas": "12 IPA",
        "JmlSiswa": "100"
      }
    ],
    "rekappenerimaan": {
      "result": true,
      "data": [
        {
          "RefBank": "Tunai",
          "Nilai": "125300000",
          "BiayaMDR": "0",
          "NetKeGO": "125300000"
        },
        {
          "RefBank": "BNI",
          "Nilai": "261000000",
          "BiayaMDR": "125000",
          "NetKeGO": "260775000"
        },
        {
          "RefBank": "BCA",
          "Nilai": "300250000",
          "BiayaMDR": "250000",
          "NetKeGO": "300000000"
        }
      ],
      "console": []
    }
  }
}
```

## Rekening

### get status

Request :

- Method : GET
- Endpoint : `/api/v1/status?search=${nama}`

Response :

```json
{
  "id": "number",
  "nama": "string"
}
```

### get list bank

Request :

- Method : GET
- Endpoint : `/api/v1/list/bank?search=${nama}`

Response :

```json
{
  "idbank": "string",
  "namabank": "string"
}
```

### get data virtual account

Request

- Method : POST
- Header : null
- Endpoint : `/api/v1/uploadva/getdata?&sortby=${NomorVA|Peruntukan|TanggalUpload|Uploader}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

  ```json
  {
    "idbank": "string",
    "status": "number"
  }
  ```

Response

```json
{
  "data": [
    {
      "IdVA": "string",
      "IdBank": "number",
      "NamaBank": "string",
      "NomorVA": "number",
      "Peruntukan": "string",
      "TanggalUpload": "string",
      "Uploader": "string",
      "IsTerpakai": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### delete data virtual account

Request

- Method : POST
- Endpoint : `/api/v1/uploadva/deldata`
- Body :

```json
{
  "idva": [1, 2, 3]
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

### download template excel

Request :

- Method : GET
- Endpoint : `/api/v1/uploadva/template-excel`

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

### tambah data virtual account

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/uploadva/adddata`
- Body :

```json
{
  "idbank": "number",
  "fileexcel": ""
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

## Transaksi

### Simulasi

#### lihat data

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/simulasi/siswa?tahunajaran=${tahunajaran}&tglawal=${tglawal}&tglakhir=${tglakhir}`

Response :

```json
{
  "data": [
    {
      "NomorInvoice": "1147231003115929",
      "TanggalDatang": "2023-10-03",
      "IdGedungDatang": "1147",
      "NoRegistrasi": "050213114702",
      "NamaLengkap": "NAJWALINA AZZAHRA",
      "HP": "082252344223",
      "IdSekolah": "121008",
      "JenjangPendidikan": "ALUMNI",
      "IdGedungBelajar": "1147",
      "TahunAjaran": "2023/2024",
      "IdSekolahKelas": "28",
      "NamaSekolahKelas": "13 ALUMNI IPA",
      "IdKelas": "271946",
      "CaraBayar": "",
      "IdBundling": "807135",
      "NamaBundling": "TWT Gap Year Saintek GO Kreasi SNBT 23/24",
      "HargaPT": "0",
      "HargaJual": "2000000",
      "TotalBayar": "2000000",
      "KodeUnik": "596",
      "NomorVA": "",
      "TanggalExpired": "2023-10-10",
      "NominalBayar": "1000000",
      "TanggalDigunakan": "2023-10-03 12:01:54",
      "Status": "Sudah Dibayar"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### cari biodata siswa untuk nambah simulasi

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/biodata?namalengkap=${namalengkap}&tanggallahir=${tanggallahir}&sortby=${NoRegistrasi|NamaLengkap|TanggalLahir|Hp|Alamat|Status}&sort=${asc|desc}&page=${page}&limit=${limit}`

Response :

```json
{
  "data": [
    {
      "NoRegistrasi": "061014000701",
      "NamaLengkap": "KEISHA ADZRA RAMADHANI",
      "JenisKelamin": "",
      "TanggalLahir": "2006-10-14",
      "Alamat": "D'AMERTA RESIDENCE BLOK E 09/12A JL. CIGANITRI",
      "Tlp": null,
      "Hp": "08112499122",
      "Hp2": "083844626004",
      "Email": "000@gmail.com",
      "Email2": "juarakonsultan@gmail.com",
      "Agama": "Islam",
      "IbuKandung": "WEWIN RICHZA FAKIH",
      "IsSiswa": "1",
      "Status": "Aktif"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get list provinsi

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/list/provinsi`

Response :

```json
{
  "data": [
    {
      "IdProvinsi": "39",
      "Provinsi": "PROVINSI ACEH"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get list kota

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/list/kota`

Response :

```json
{
  "data": [
    {
      "IdPenanda": "194",
      "Penanda": "AIKMEL"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get list tahun ajaran

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/list/tahunajaran`

Response :

```json
{
  "data": [
    {
      "TahunAjaran": "2024/2025",
      "IsDefault": "N"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Pendaftaran

#### lihat data siswa

Request

- Method : GET
- Endpoint : `api/v1/gokasir/pendaftaran/invoice?invoice=${nomorinvoice}`

Response

```json
{
  "data": [
    {
      "NomorInvoice": "0002231003103926",
      "TanggalDatang": "2023-10-03",
      "IdGedungDatang": "1147",
      "NoRegistrasi": "051231114789",
      "NamaLengkap": "uji coba keuangan",
      "HP": "08112385459",
      "HPOrtu": "08112385459",
      "Email": "tiaraayunda373@gmai.com",
      "EmailOrtu": "tiara@gmail.com",
      "IdSekolah": "392716",
      "NamaSekolah": "HOMESCHOOLING MILENIAL UNGGUL",
      "JenjangPendidikan": "SMA",
      "IdGedungBelajar": "2",
      "TahunAjaran": "2023/2024",
      "IdSekolahKelas": "14",
      "NamaSekolahKelas": "12 SMA IPA",
      "IdKelas": "269738",
      "CaraBayar": "",
      "JenisBayar": "",
      "IdBundling": "766519",
      "NamaBundling": "TWT 12 SMA IPA K13R 4P 23/24",
      "Produk": {
        "data": [
          {
            "id": 32664,
            "nama": "23_e- Buku Sakti Empati Mandiri 12 SMA IPA K13R"
          },
          {
            "id": 32733,
            "nama": "23_e- Buku Sakti Empati Wajib 12 SMA IPA K13R"
          }
        ],
        "hargapt": 200000,
        "hargajual": 9500000,
        "hargaproduk": 9700000
      },
      "Diskon": {
        "data": [
          {
            "id": "22767683",
            "nama": "Diskon Anak Kandung Guru_",
            "ispart": "1",
            "relatif": "Y",
            "diskonrp": 0,
            "issyarat": "1",
            "kelompok": "Diskon Anak Kandung Guru",
            "tglakhir": "2024-06-30",
            "diskonrpacc": 4750000,
            "diskonpersen": 50,
            "idjenisdiskon": "810"
          }
        ],
        "diskonlunas": 0,
        "totaldiskon": 0,
        "iddiskonlunas": 0,
        "totaldiskonpt": 0,
        "totaldiskonjual": 0,
        "idjenisdiskonlunas": "",
        "ispersendiskonlunas": false
      },
      "TotalBayar": "9700000",
      "KodeUnik": "0",
      "TotalYangDiBayarkan": "9700000",
      "SkemaCicilan": [
        {
          "jumlah": 200000,
          "cicilanke": 0,
          "jumlahacc": 200000,
          "jatuhtempo": "2023-10-03",
          "keterangan": "Pendaftaran"
        },
        {
          "jumlah": 4750000,
          "cicilanke": 1,
          "jumlahacc": 4750000,
          "jatuhtempo": "2023-10-03",
          "keterangan": "Cicilan 1"
        },
        {
          "jumlah": 2850000,
          "cicilanke": 2,
          "jumlahacc": 0,
          "jatuhtempo": "2023-11-03",
          "keterangan": "Cicilan 2"
        },
        {
          "jumlah": 1900000,
          "cicilanke": 3,
          "jumlahacc": 0,
          "jatuhtempo": "2023-12-03",
          "keterangan": "Cicilan 3"
        }
      ],
      "IdPola": "2",
      "PolaCicilan": {
        "1": 50,
        "2": 30,
        "3": 20
      },
      "TanggalExpired": "2023-10-10",
      "Status": "Kadaluarsa",
      "IdPembelian": null,
      "HargaSebelum": "9500000",
      "HargaPenyesuaian": "0"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### cari nomor invoice

Request :

- Method : GET
- Endpoint : `api/v1/go-kasir/pendaftaran/carinomorinvoice?tanggal=${tanggal}&key=${nama}`

Response :

```json
{
  "data": [
    {
      "NomorInvoice": "0002231111180527",
      "NoRegistrasi": "051231114785",
      "TanggalLahir": "2005-12-31",
      "TanggalDatang": "2023-11-11",
      "Status": "Belum",
      "NamaLengkap": "Uji Coba Keuangan 4",
      "GedungDatang": "BANDUNG - PW 34",
      "GedungBelajar": "BANDUNG - PW 36-B",
      "NamaBundling": "TWT 12 SMA IPA K13R 4P 23/24"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Pembayaran Cicilan

#### cek pembayaran

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/pembayaran?noregistrasi=${noreg}`

Response :

```json
{
  "data": [
    {
      "NoRegistrasi": "061014004401",
      "IdPembelian": "1828873",
      "NamaLengkap": "Risa Oktaviana Ramadhani",
      "TahunAjaran": "2023/2024",
      "NamaGedung": "MERDEKA 107 B",
      "TanggalDaftar": "2023-07-25",
      "SekolahKelas": "12 SMA IPA",
      "NamaKelas": null,
      "IdBundling": "798631",
      "NamaBundling": "TWT 12 SMA IPA TOBK Promosi",
      "StatusBayar": "LUNAS",
      "HargaPT": "0",
      "HargaJual": "50000",
      "TotalHarga": "50000",
      "Diskon": [
        {
          "id": 2266715,
          "st": "Aktif",
          "jml": 49999
        }
      ],
      "Pembayaran": [
        {
          "id": 8528178,
          "byr": 0,
          "jml": 0
        },
        {
          "id": 8528179,
          "byr": 1,
          "jml": 1
        }
      ],
      "JatuhTempo": null,
      "HP": "08588859717908",
      "Email": "risaoktaviana000@gmail.com",
      "HPOrtu": "08124088812908",
      "EmailOrtu": "0@GMAIL.COM",
      "NoPerjanjian": null,
      "TotalDiskon": 49999,
      "TotalPembayaran": 1,
      "HarusBayar": 1,
      "JumlahBayar": 1,
      "Sisa": 0
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## Transaksi Artikel

### Simulasi Artikel

#### Get DataTabel Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/transaksi-artikel/simulasi/datatabel?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?tgl_awal={value}?tgl_akhir={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "nomorInvoice": "0093230923143303",
            "tanggalDatang": "2023-09-23",
            "idGedungDatang": "unique",
            "noRegistrasi": "number",
            "namaLengkap": "string",
            "hp": "number",
            "idSekolah": "unique",
            "jenjangPendidikan": "string",
            "idGedungBelajar": "unique",
            "tahunAjaran": "string",
            "idSekolahKelas": "unique",
            "namaSekolahKelas": "string",
            "idKelas": "unique",
            "caraBayar": "",
            "idBundling": "unique",
            "namaBundling": "string",
            "hargaPT": "number",
            "hargaJual": "number",
            "totalBayar": "number",
            "kodeUnik": "unique",
            "nomorVA": "number",
            "tanggalExpired": "2023-09-30",
            "nominalBayar": "number",
            "tanggalDigunakan": null,
            "status": "enum",
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

#### Get Biodata untuk Tambah Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata?nama_lengkap={value}?tgl_lahir={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "NoRegistrasi": "unique",
          "NamaLengkap": "string",
          "JenisKelamin": "enum",
          "TanggalLahir": "2006-10-14",
          "alamat": "string",
          "tlp": "number",
          "hp": "number",
          "hp2": "number",
          "email": "jasminechrisna14@gmail.com",
          "email2": "jasminechrisna14@gmail.com",
          "agama": "enum",
          "ibuKandung": "string",
          "isSiswa": "boolean",
          "status": "enum"  
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Get Biodata Detail => Info siswa Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "noregistrasi": "unique",
          "namalengkap": "string",
          "namapanggilan": "string",
          "provinsikelahiran": "unique",
          "namaprovinsikelahiran": "string",
          "kotakelahiran": "unique",
          "namakotakelahiran": "string",
          "jeniskelamin": "enum",
          "tanggallahir": "2006-10-14",
          "namaibukandung": "string",
          "pekerjaanortu": "string",
          "agama": "enum",
          "golongandarah": null,
          "alamat": "Perumahan Griya Asri 2, Jl. Flamboyan Blok J26 no.48 Rt 08/Rw 40 \n",
          "provinsialamat": "12",
          "namaprovinsialamat": "PROVINSI JAWA BARAT",
          "kotaalamat": "156",
          "namakotaalamat": "KABUPATEN BEKASI",
          "kecamatanalamat": "313",
          "kelurahan": "2664",
          "kodepos": "17510",
          "statuskepemilikan": null,
          "notlp": null,
          "nohpsiswa": "089613312329",
          "nohportu": "081213009680",
          "emailsiswa": "jihanoktavia14@gmail.com",
          "emailortu": "sn418103@gmail.com",
          "status": "Aktif",
          "hubungan": "Ayah"  
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Get Biodata Detail => Kartu Identitas Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/kartu-identitas?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "idIdentitas": "55234",
          "jenisKartuIdentitas": "KTP",
          "image_kartu_identitas": "string",
          "idProvinsi": "1",
          "provinsi": "PROVINSI ACEH",
          "idKota": "1",
          "kota": "KABUPATEN ACEH BARAT"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Get Biodata Detail => Saudara Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/saudara?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "idBiodataSaudara": "529",
          "noRegistrasi": "61014004401",
          "hubungan": "KAKAK",
          "nama": "jamal",
          "tanggalLahir": "2023-11-14",
          "umur": "0 Thn"  
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Update Biodata => info Biodata

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "noregistrasi": "unique",
          "namalengkap": "string",
          "namapanggilan": "string",
          "provinsikelahiran": "unique",
          "namaprovinsikelahiran": "string",
          "kotakelahiran": "unique",
          "namakotakelahiran": "string",
          "jeniskelamin": "enum",
          "tanggallahir": "2006-10-14",
          "namaibukandung": "string",
          "pekerjaanortu": "string",
          "agama": "enum",
          "golongandarah": null,
          "alamat": "Perumahan Griya Asri 2, Jl. Flamboyan Blok J26 no.48 Rt 08/Rw 40 \n",
          "provinsialamat": "12",
          "namaprovinsialamat": "PROVINSI JAWA BARAT",
          "kotaalamat": "156",
          "namakotaalamat": "KABUPATEN BEKASI",
          "kecamatanalamat": "313",
          "kelurahan": "2664",
          "kodepos": "17510",
          "statuskepemilikan": null,
          "notlp": null,
          "nohpsiswa": "089613312329",
          "nohportu": "081213009680",
          "emailsiswa": "jihanoktavia14@gmail.com",
          "emailortu": "sn418103@gmail.com",
          "status": "Aktif",
          "hubungan": "Ayah"
        }
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Update Biodata => Kartu Identitas

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/kartu-identitas?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "jenis_kartu_identitas": "string",
          "idprovinsi": "unique",
          "idkota": "unique", //generate dari tanggal lahir
          "image_kartu_identitas": "string"
        }
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Update Biodata => Saudara

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/saudara?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "nama": "string",
          "tanggallahir": "2006-10-14",
          "umur": "number", //generate dari tanggal lahir
          "hubungan": "Ayah"
        }
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Delete Biodata => Saudara

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/saudara?no_register={value}?id_identitas={value}`,
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

#### Delete Biodata => Kartu Identitas

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/kartu-identitas?no_register={value}?id_saudara={value}`,
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


### Pembayaran Artikel

#### Get Data Invoice Pembayaran Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/pembayaran-artikel/invoice?no_invoice={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "nomorInvoice": "0002231003103926",
          "tanggalDatang": "2023-10-03",
          "idGedungDatang": "1147",
          "noRegistrasi": "051231114789",
          "namaLengkap": "uji coba keuangan",
          "hp": "08112385459",
          "hpOrtu": "08112385459",
          "email": "tiaraayunda373@gmai.com",
          "emailOrtu": "tiara@gmail.com",
          "idSekolah": "392716",
          "namaSekolah": "HOMESCHOOLING MILENIAL UNGGUL",
          "jenjangPendidikan": "SMA",
          "idGedungBelajar": "2",
          "tahunAjaran": "2023/2024",
          "idSekolahKelas": "14",
          "namaSekolahKelas": "12 SMA IPA",
          "idKelas": "269738",
          "caraBayar": "",
          "jenisBayar": "",
          "idBundling": "766519",
          "namaBundling": "TWT 12 SMA IPA K13R 4P 23/24",
          "produk": {
              "data": [
                  {
                      "id": 32664,
                      "nama": "23_e- Buku Sakti Empati Mandiri 12 SMA IPA K13R"
                  },
              ],
              "hargapt": 200000,
              "hargajual": 9500000,
              "hargaproduk": 9700000
          },
          "c_Diskon": {
              "data": [
                  {
                      "id": "22767683",
                      "nama": "Diskon Anak Kandung Guru_",
                      "ispart": "1",
                      "relatif": "Y",
                      "diskonrp": 0,
                      "issyarat": "1",
                      "kelompok": "Diskon Anak Kandung Guru",
                      "tglakhir": "2024-06-30",
                      "diskonrpacc": 4750000,
                      "diskonpersen": 50,
                      "idjenisdiskon": "810"
                  }
              ],
              "diskonlunas": 0,
              "totaldiskon": 0,
              "iddiskonlunas": 0,
              "totaldiskonpt": 0,
              "totaldiskonjual": 0,
              "idjenisdiskonlunas": "",
              "ispersendiskonlunas": false
          },
          "totalBayar": "9700000",
          "kodeUnik": "0",
          "totalYangDiBayarkan": "9700000",
          "skemaCicilan": [
              {
                  "jumlah": 200000,
                  "cicilanke": 0,
                  "jumlahacc": 200000,
                  "jatuhtempo": "2023-10-03",
                  "keterangan": "Pendaftaran"
              },
          ],
          "idPola": "number",
          "polaCicilan": {
              "1": 50,
              "2": 30,
              "3": 20
          },
          "tanggalExpired": "2023-10-10",
          "status": "enum",
          "idPembelian": "unique",
          "hargaSebelum": "number",
          "hargaPenyesuaian": "number"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```


#### Get Datatabel Nomor Invoice Pembayaran Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/pembayaran-artikel/invoice/no_invoice?tanggal={value}?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "NomorInvoice": "0002231111180527",
          "NoRegistrasi": "051231114785",
          "TanggalLahir": "2005-12-31",
          "TanggalDatang": "2023-11-11",
          "Status": "Belum",
          "NamaLengkap": "Uji Coba Keuangan 4",
          "GedungDatang": "BANDUNG - PW 34",
          "GedungBelajar": "BANDUNG - PW 36-B",
          "NamaBundling": "TWT 12 SMA IPA K13R 4P 23/24"
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


## Dokument Diskon

### Unggah Dokument Diskon

#### Get DataTabel Unggah Dokument Diskon

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/unggah/datatabel?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?tingkat_kelas={value}?kota={value}?gedung={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "idPembelian": "unique",
            "namaGedung": "PW 36-B",
            "noRegistrasi": "060514000201",
            "nomorInvoice": "0002231003161146",
            "namaLengkap": "ADELYA SELFI LISYANA",
            "namaKelas": "12-IPS-R-N-102",
            "namaBundling": "TWT 12 SMA IPS K13R 4P 23/24",
            "statusAjuan": "enum",
            "tglbayarpertama": "2023-10-03",
            "lamabayarpertama": 42,
            "tanggalTerakhirUnggah": "-",
            "action": "Lihat Ajuan",
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


#### Get Diskon Unggah Dokument Diskon

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/unggah/diskon?id_pembelian={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "idAmbilDiskon": "unique",
          "ajuanDiskon": "Diskon Pemuda 5%_",
          "keterangan": "string",
          "isNeedDocument": "boolean",
          "tanggalUnggah": null,
          "dokumenDiskon": null,
          "status": "enum"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```


### Validasi Dokument Diskon

#### Get DataTabel Validasi Dokument Diskon

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/validasi/datatabel?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?tingkat_kelas={value}?kota={value}?gedung={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "idPembelian": "unique",
            "namaGedung": "PW 36-B",
            "noRegistrasi": "060514000201",
            "nomorInvoice": "0002231003161146",
            "namaLengkap": "ADELYA SELFI LISYANA",
            "namaKelas": "12-IPS-R-N-102",
            "namaBundling": "TWT 12 SMA IPS K13R 4P 23/24",
            "statusAjuan": "enum",
            "tglbayarpertama": "2023-10-03",
            "lamabayarpertama": 42,
            "tanggalTerakhirUnggah": "-",
            "action": "Lihat Ajuan",
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


#### Get Detail Validasi Dokument Diskon (Skema Pembayaran)

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/validasi/detail?id={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "id": "8711535",
          "jumlah": "200000",
          "keterangan": "PENDF.",
          "cicilanke": "0",
          "jatuhtempo": "2023-06-07",
          "sudahbayar": "200000",
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


#### Get Detail Validasi Dokument Diskon (Diskon)

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/validasi/diskon?id={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "idJenisDiskon": "unique",
            "idAmbilDiskon": "unique",
            "idDiskonKeluarkan": "unique",
            "isSyarat": "boolean",
            "isPart": "boolean",
            "diskonPersen": null,
            "isRelatif": "boolean",
            "diskonRP": "49999",
            "diskonRPAsli": "49999",
            "namaReferensi": "",
            "filePrasyarat": [],
            "status": "ACC",
            "statusAsli": "Aktif",
            "namaDiskon": "Diskon TOBK Promosi 100%_",
            "isACC": "1",
            "tanggalUnggah": null,
            "isACCASli": "1"
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


## BASTUP

### TAMBAH DATA BASTUP

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/bastup`
- Header : null
- Body :

```json
{
  "nomorBastup": "string",
  "tanggalTerimaUang": "string",
  "yangMenyerahkan": "string",
  "fileDokumen": "string"
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

### GET DATA TABLE LIST BASTUP

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastup/${params.tanggalAwal}/${params.tanggalAkhir}/${params.status}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "NoBASTUP": "string",
      "TanggalTerima": "date and time",
      "NIKPenyetor": "string",
      "NamaPenyetor": "string",
      "NIKPenerima": "string",
      "NamaPenerima": "string",
      "NamaFile": "string",
      "Status": "string",
      "Jumlah": "number"
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

### UBAH BASTUP

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/bastup`
- Header : null
- Body :

```json
{
  "nomorBastup": "string",
  "tanggalTerimaUang": "string",
  "yangMenyerahkan": "string",
  "fileDokumen": "string"
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

### GET DATA LIST SISWA BASTUP

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/siswabastup`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "namaSiswa": "string",
      "jumlah": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### TAMBAH SISWA BERDASARKAN KODE BASTUP

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/siswabastup`
- Header : null
- Body :

```json
{
  "nomorBastup": "string",
  "namaSiswa": "string",
  "jumlahUang": "number"
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

### UPDATE STATUS LENGKAP dan TIDAK LENGKAP

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/bastup/status/${params.kodeBastup}`
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

### KIRIM DATA BASTUP

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/bastup/${params.kodeBastup}`
- Header : null
- Body :

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

### DELETE DATA BASTUP

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/bastup/${params.id}`
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

### GET DATA TABLE VALIDASI BASTUP

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastup/${params.tanggalAwal}/${params.tanggalAkhir}/${params.status}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "NoBASTUP": "string",
      "TanggalTerima": "date and time",
      "NIKPenyetor": "string",
      "NamaPenyetor": "string",
      "NIKPenerima": "string",
      "NamaPenerima": "string",
      "NamaFile": "string",
      "Status": "string",
      "Jumlah": "number"
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

### UPDATE APPROVE BASTUP

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/bastup/${params.id}`
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

## BASTPH

### TAMBAH DATA BASTPH

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/bastph`
- Header : null
- Body :

```json
{
  "nomorBashtph": "string",
  "tanggalSerahTerima": "string",
  "waktuSetoran": "string",
  "jumlahCash": "number",
  "penerimaSetoran": "string"
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

### GET DATA TABLE TRANSAKSI BASTUP

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastup/transaksi/${params.tanggalAwal}/${params.tanggalAkhir}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "namaBundling": "string",
      "noKwitansi": "string",
      "noBastup": "string",
      "tanggalTransaksi": "string",
      "jumlahCash": "string"
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

### GET DATA TABLE BASTPH

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastph/${params.tanggalAwal}/${params.tanggalAkhir}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "nomorBastph": "string",
      "tanggalSerahTerima": "date and time",
      "penerimaSetoran": "string",
      "jenisSetoran": "string",
      "jumlahCash": "string",
      "status": "string"
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

### DELETE DATA BASTPH

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/bastph/${params.id}`
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

### KIRIM DATA BASTPH

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/bastph/${params.kodeBastph}`
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

### GET DATA TABLE LIST VALIDASI BASHTPH

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastph/${params.tanggalAwal}/${params.tanggalAkhir}/${params.status}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "NoBASTPH": "string",
      "TanggalSerahTerima": "date and time",
      "NIKPenerima": "string",
      "NamaPenerima": "string",
      "Status": "string",
      "JumlahPenerimaan": "string",
      "JenisWaktuPenerimaan": "string"
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

## LSPH

### TAMBAH DATA LSPH

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/lsph`
- Header : null
- Body :

```json
{
  "nomorLsph": "string", // auto generated
  "namaBank": "string",
  "noRekening": "string",
  "tanggalSetor": "date and time"
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

### GET LIST BANK

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/banks`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "IdBank": "string",
      "NamaBank": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### GET ISI BASTPH BY KODE LPH

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/lph/${params.kodeLph}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "NoBASTPH": "string",
      "TanggalSerahTerima": "date and time",
      "JenisWaktuPenerimaan": "string",
      "NIKPenyetor": "string",
      "NamaPenyetor": "string",
      "Status": "string",
      "JumlahPenerimaan": "mumber",
      "JumlahSetor": "number",
      "SisaSetor": "number",
      "RencanaSetor": "number"
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

### TAMBAH RENCANA SETORAN BY KODE LSPH

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/lsph/setsetoran/${params.kodeLsph}`
- Header : null
- Body :

```json
{
  "nomorBastph": "string",
  "sisaSetor": "number",
  "rencanaSetor": "number"
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

### KIRIM STATUS LSPH

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/lsph/status/${params.kodeLsph}`
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

### DELETE DATA LSPH

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/lsph/${params.kodeLsph}`
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

## MDR

### get list mdr

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/list/mdr?sortby=${metode|Jenis|NamaBankGO|NamaBankCustomer|Tipe|Persen|Nominal|Keterangan|KodeRekening}&sort=${asc|desc}&page=${page}&limit=${limit}`

Response :

```json
{
  "data": [
    {
      "IdMDR": "9",
      "Metode": "INSTALLMENT 6 BULAN",
      "Jenis": "Website",
      "IdBankGO": "4",
      "NamaBankGO": "MANDIRI",
      "IdBankCustomer": "4",
      "NamaBankCustomer": "MANDIRI",
      "Tipe": "PERSEN",
      "Persen": "4.00",
      "Nominal": "0",
      "Keterangan": "MANDIRI IPG",
      "KodeRekening": "2102002"
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

> **NOTE**
> Tidak ada di gokasir existing.
>
> Ex :
>
> ##### GET METODE
>
> - Kartu debit
> - Kartu kredit
> - transfer
>
> ##### GET JENIS
>
> - Antar Rekening
> - Payment Gateway
> - Virtual Account
>
> #### GET TIPE
>
> - NOMINAL
> - PERSEN

### get metode

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/list/metode?search=${name}`

Response :

```json
{
  "data": [
    {
      "id": "number",
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

### get jenis

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/list/jenis?search=${name}`

Response :

```json
{
  "data": [
    {
      "id": "number",
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

### get tipe

Request :

- Method : GET
- Endpoint : `api/v1/gokasir/list/tipe?search=${name}`

Response :

```json
{
  "data": [
    {
      "id": "number",
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

> **_NOTE:_** hanya prediksi, belum di coba di gokasir existing.

### add list mdr

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/mdr/add`
- Body :

```json
{
  "id_metode": "number",
  "id_jenis": "number",
  "id_bank_go": "number",
  "id_bank_go": "number",
  "id_bank_customer": "number",
  "id_tipe": "number",
  "id_tipe": "number",
  "persen": "number",
  "nominal": "number",
  "kode_rekening": "number",
  "keterangan": "number"
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

### edit list mdr

Request :

- Method : PATCH
- Endpoint : `api/v1/gokasir/mdr/edit/:id`
- Body :

```json
{
  "id_mdr": "number",
  "id_metode": "number",
  "id_jenis": "number",
  "id_bank_go": "number",
  "id_bank_go": "number",
  "id_bank_customer": "number",
  "id_tipe": "number",
  "id_tipe": "number",
  "persen": "number",
  "nominal": "number",
  "kode_rekening": "number",
  "keterangan": "number"
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

### delete list mdr

Request :

- Method : DELETE
- Endpoint : `api/v1/gokasir/mdr/delete/:id`
- Body :

```json
{
  "id_mdr": "number"
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

## Go Expert

### Registrasi

Request :

- Method : GET
- Endpoint : `api/v1/goexpert/registrasi?noregistrasi=${noreg}`

Response :

```json
{
  "data": [
    {
      "pembayaran": [
        {
          "NoRegistrasi": "050213114702",
          "IdPembelian": "1886949",
          "NamaLengkap": "NAJWALINA AZZAHRA",
          "TahunAjaran": "2023/2024",
          "NamaGedung": "PW 34",
          "TanggalDaftar": "2023-10-03",
          "SekolahKelas": "13 ALUMNI IPA",
          "NamaKelas": "13-ALUMNI-R-N-ONLINE",
          "IdBundling": "807135",
          "NamaBundling": "TWT Gap Year Saintek GO Kreasi SNBT 23/24",
          "StatusBayar": "LUNAS",
          "HargaPT": "0",
          "HargaJual": "2000000",
          "TotalHarga": "2000000",
          "Diskon": [
            {
              "id": 2336532,
              "st": "Aktif",
              "jml": 1000000
            }
          ],
          "Pembayaran": [
            {
              "id": 8763815,
              "byr": 0,
              "jml": 0
            },
            {
              "id": 8763816,
              "byr": 1000000,
              "jml": 1000000
            },
            {
              "id": 8763817,
              "byr": 0,
              "jml": 0
            }
          ],
          "JatuhTempo": null,
          "HP": "082252344223",
          "Email": "najwanet04@gmail.com",
          "HPOrtu": "0811587750",
          "EmailOrtu": "ghozali.mh@gmail.com",
          "NoPerjanjian": null,
          "TotalDiskon": 1000000,
          "TotalPembayaran": 1000000,
          "HarusBayar": 1000000,
          "JumlahBayar": 1000000,
          "Sisa": 0
        }
      ],
      "gokreasi": [
        {
          "NoRegistrasi": "050213114702",
          "Email": "najwanet04@gmail.com",
          "NamaLengkap": "NAJWALINA AZZAHRA",
          "IdSekolahKelas": "28",
          "NamaSekolahKelas": "13 ALUMNI IPA",
          "Siapa": "SISWA",
          "Status": "aktif",
          "NomorHP": "082252344223",
          "IsDevice": "1",
          "TerakhirLogin": "2023-10-03 12:32:43"
        },
        {
          "NoRegistrasi": "050213114702",
          "Email": "najwanet04@gmail.com",
          "NamaLengkap": "NAJWALINA AZZAHRA",
          "IdSekolahKelas": "28",
          "NamaSekolahKelas": "13 ALUMNI IPA",
          "Siapa": "ORTU",
          "Status": "aktif",
          "NomorHP": "0811587750",
          "IsDevice": "1",
          "TerakhirLogin": "2023-10-03 15:08:50"
        }
      ]
    }
  ]
}
```


## Bimker

### DAFTAR BIMKER

#### get kewilayahan by kota

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/list/kewilayahanbykota`
- Body :

```json
{
  "id_kota": "string"
}
```

Response :

```json
{
  "data": [
    {
      "IdKewilayahan": "3",
      "NamaKewilayahan": "Cabang"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get komar

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/list/komar`
- Body :

```json
{
  "id_kewilayahan": "string",
  "id_kota": "string"
}
```

Response :

```json
{
  "data": [
    {
      "IdKomar": "727",
      "NamaKomar": "L.U Adisucipto 134, Mt. Haryono 6, Moewardi 17"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### Daftar Bimker

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/daftarbimker/getdata?sortby=${Penanda|NamaKomar|Deskripsi|NamaSekolah|SekolahKelas|PerkiaraanJumSis|JumSis|TanggalAwal|TanggalAkhir|Status}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "id_kota": "string",
  "id_kewilayahan": "string",
  "id_komar": "string",
  "status": "string",
  "tahunajaran": "string"
}
```

Response :

```json
{
  "data": [
    {
      "IdKerjasama": "707",
      "IdPenanda": "6",
      "Penanda": "SURAKARTA",
      "IdKomar": "2136",
      "NamaKomar": "MT. Haryono 6",
      "TahunAjaran": "2023/2024",
      "NamaChannel": "Dra. Nurul Qomariah, M.Pd.",
      "Telp": "081802599935",
      "IsDenganSekolah": "1",
      "IdSekolah": "219349",
      "NamaSekolah": "MTSN 1 SURAKARTA",
      "JenjangPendidikan": "MTs",
      "IdDistrict": "199",
      "District": "KOTA SURAKARTA",
      "IdProvinsi": "15",
      "Provinsi": "PROVINSI JAWA TENGAH",
      "IdSekolahKelas": "7",
      "SekolahKelas": "7 SMP UMUM",
      "NilaiKerjasama": "52500000",
      "TahapanPembayaran": "[{\"tahap\": 1, \"jumlah\": 30000000, \"tanggal\": \"2023-09-19\"}, {\"tahap\": 2, \"jumlah\": 22500000, \"tanggal\": \"2024-01-24\"}]",
      "BiayaOperasional": "3000000",
      "PerkiaraanJumSis": "30",
      "Jumsis": "30",
      "BiayaPerSiswa": "1750000",
      "TglJatuhTempo1": "2023-09-19",
      "Deskripsi": "BIMKER MTsN 1 SURAKARTA KELAS 7",
      "TanggalAwal": "2023-09-19",
      "TanggalAkhir": "2024-05-28",
      "JumlahPertemuan": "56",
      "JumlahPertemuanOffline": "56",
      "JumlahPertemuanOnline": "0",
      "JumlahTOBK": "3",
      "JumlahTOBC": "0",
      "Pengali": "1.00",
      "PengaliReal": "1.00",
      "IdBundling": "1222677",
      "NamaBundling": "TWT 7 SMP Bimker MTsN 1 Surakarta KMerdeka 23/24",
      "HargaPT": "0",
      "HargaTotal": "1750000",
      "FileMOU": "ff274912f1d12d2f9df0c673d7f030c8_230925073158.pdf",
      "Status": "Setuju",
      "Updater": "1302501109",
      "LastUpdate": "2023-09-26 10:37:08"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get pembayaran bimker

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/daftarbimker/getpembayaranbimker?sortby=${TglJthTempo|JmlBayar}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "id_kerjasama": "number"
}
```

Response :

```json
{
  "data": [
    {
      "TglJthTempo": "2023-09-26",
      "JmlBayar": "30000000",
      "TglKadaluarsa": "-"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get daftar siswa bimker

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/daftarbimker/getdaftarsiswabimbker?sortby=${NamaSiswa|NamaKelas|JmlBayar}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "id_kerjasama": "number"
}
```

Response :

```json
{
  "data": [
    {
      "NamaSiswa": "080525022801 - MUHAMMAD ABDULLAH ZAIN ZAIN",
      "NamaKelas": "10-UMUM-R-B-32",
      "JmlBayar": "2000000",
      "BuktiPembayaran": ""
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get file MOU

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/daftarbimker/getfilemou/:id`
- Body :

```json
{
  "id_kerjasama": "number"
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



# MODUL Go Produk

## Komponen Produk

### Bidang
Request :

- Method : GET
- Endpoint : `/api/v1/bidang`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
             {
            "id": "number",
            "name": "name"
        },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
### Get Komponen Produk

Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/komponenproduk?status={value}&page={value}&per_page={value}`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
                "c_IdProduk": "number",
                "c_IdJenisProduk": "number",
                "c_NamaJenisProduk": "String",
                "c_IdKurikulum": "number",
                "c_NamaKurikulum": "String",
                "c_IdSekolahKelas": "number",
                "c_NamaSekolahKelas": "String",
                "c_IdBidang": "number",
                "c_NamaBidang": "String",
                "c_IdJenisKelas": "number",
                "c_NamaJenisKelas": "String",
                "c_NamaProduk": "String",
                "c_Keterangan": "String",
                "c_Status": "String"
            }
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
### Create Komponen Produk

Request :

- Method : post
- Endpoint : `/api/v1/goproduk/komponenproduk`,
- Header : null
- Body :
```json
{
  "idjenisproduk": "number",
  "idkurikulum": "number",
  "idtingkatkelas": "number",
  "idbidang": "number",
  "idlayanan": "number",
  "namaproduk": "String",
  "keterangan": "String"
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
### Update Komponen Produk

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/komponenproduk/{idProduk}`,
- Header : null
- Body :
```json
{ "idProduk":"number",
  "idjenisproduk": "number",
  "idkurikulum": "number",
  "idtingkatkelas": "number",
  "idbidang": "number",
  "idlayanan": "number",
  "namaproduk": "String",
  "keterangan": "String"
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
### Delete Komponen Produk

Request :

- Method : Delete
- Endpoint : `/api/v1/goproduk/komponenproduk/{idProduk}`,
- Header : null
- Body :

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
### Update Status Komponen Produk

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/komponenproduk/ajukan`,
- Header : null
- Body :
```json
{ "idProduk":"number"}

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
### Validasi Komponen Produk

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/komponenproduk/validasi`,
- Header : null
- Body :
```json
{ 
    "idProduk":"number",
    "Status":"bolean",
    "user_id" :"String"
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

## Komponen Produk MIX

### get List Produk Mix

Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/komponenprodukmix?status={value}&iskerjasama={value}&idkurikulum={value}&idlayanan={value}&idtingkatkelas={value}&page={value}&per_page={value}`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
                "c_IdProdukMix": "number",
                "c_NamaProdukMix": "String",
                "c_IdKurikulum": "number",
                "c_NamaKurikulum": "String",
                "c_IdSekolahKelas": "number",
                "c_NamaSekolahKelas": "String",
                "c_IdJenisKelas": "number",
                "c_NamaJenisKelas": "String",
                "c_IsKerjaSama": "Bolean",
                "c_IsJaminan": "bolean",
                "c_IsJenisPertemuan": "bolean",
                "c_JenisPertemuan": "String",
                "c_JumS1": "number",
                "c_JumS2": "number",
                "c_JumS3": "number",
                "c_Zona": "number",
                "c_KodeUnik": "String",
                "c_TotalIsi": "number",
                "c_Status": "String, bolean"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

### get Detail Produk Mix

Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/komponenprodukmix/{idProdukmix}`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
            "c_IdProduk": "number",
            "c_IdJenisProduk":"number",
            "c_NamaJenisProduk":"string",
            "c_IdKurikulum": "number",
            "c_NamaKurikulum": "string",
            "c_IdSekolahKelas":"number",
            "c_NamaSekolahKelas": "string",
            "c_IdJenisKelas": "number",
            "c_NamaJenisKelas": "string",
            "c_NamaProduk": "string",
            "c_Index": "number",
            "c_Jumlah": "number",
        },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
### Create Produk Mix

Request :

- Method : POST
- Endpoint : `/api/v1/goproduk/komponenprodukmix`,
- Header : null
- Body :
```json
    {
    "tingkatkelas": "number",
    "layanan": "number",
    "kerjasama": "Bolean",
    "jaminan": "bolean",
    "idkurikulum": "number",
    "jums1": "number",
    "jums2": "number",
    "jums3":"number",
    "kodeunik": "string",
    "namaprodukmix": "string",
    "jenispertemuan": "number",
    "zona": "number"
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


### Update Produk Mix

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/komponenprodukmix`,
- Header : null
- Body :
```json
    {
        "idProdukMix":"number",
        "tingkatkelas": "number",
        "layanan": "number",
        "kerjasama": "Bolean",
        "jaminan": "bolean",
        "idkurikulum": "number",
        "jums1": "number",
        "jums2": "number",
        "jums3":"number",
        "kodeunik": "string",
        "namaprodukmix": "string",
        "jenispertemuan": "number",
        "zona": "number"
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


### Delete Produk Mix

Request :

- Method : Delete
- Endpoint : `/api/v1/goproduk/komponenprodukmix/{idProdukMix}`,
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

### Update Status Komponen Produk MIX

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/komponenprodukmix/ajukan`,
- Header : null
- Body :
```json
{ "idProdukmix":"number"}

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



### Validasi/Pengesahan Komponen Produk

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/komponenprodukmix/validasi`,
- Header : null
- Body :
```json
{ 
    "idProdukmix":"number",
    "Status":"String",
    "user_id" :"String"
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

## jenis Diskon

### Get List Jenis diskon

Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/jenisdiskon?kelompok={value}&page={value}&per_page={value}`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
           {
            "c_IdJenisDiskon": "number",
            "c_InisialDiskon": "string",
            "c_IdBidangApprove": "number",
            "c_NamaDiskon": "string",
            "c_IsRelatif": "bolean",
            "c_PartDiskon": "bolean",
            "c_Prioritas": "number",
            "c_Kelompok": "string",
            "c_IsNeedDocument": "bolean",
            "c_Ikatan": "string",
            "c_Status": "string",
            "c_Updater": "string",
            "c_LastUpdate": "string, datetime",
            "c_Insert":  "string, datetime",
            "c_NamaBidang": "string",
        },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
### Create Jenis diskon

Request :

- Method : POST
- Endpoint : `/api/v1/goproduk/jenisdiskon`,
- Header : null
- Body :
```json
        {
            "cInisialDiskon": "string",
            "cIdBidangApprove":"number",
            "cNamaDiskon": "string",
            "cIsRelatif": "bolean",
            "cPartDiskon": "bolean",
            "cPrioritas": "Number",
            "cKelompok": "string",
            "cIsNeedDocument": "bolean",
            "cIkatan": "string",
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


### Edit Jenis diskon

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/jenisdiskon`,
- Header : null
- Body :
```json
        {
            "IdJenisDiskon": "Number",
            "cInisialDiskon": "string",
            "cIdBidangApprove":"number",
            "cNamaDiskon": "string",
            "cIsRelatif": "bolean",
            "cPartDiskon": "bolean",
            "cPrioritas": "Number",
            "cKelompok": "string",
            "cIsNeedDocument": "bolean",
            "cIkatan": "string",
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

### Delete Jenis diskon

Request :

- Method : Delete
- Endpoint : `/api/v1/goproduk/jenisdiskon/{idjenisDiskon}`,
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



### Update Status jenis diskon

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/jenisdiskon/ajukan`,
- Header : null
- Body :
```json
{ "idProduk":"number"}

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

### Validasi Jenis Diskon

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/jenisdiskon/validasi`,
- Header : null
- Body :
```json
{ 
    "idProduk":"number",
    "Status":"String",
    "user_id" :"String"
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


## Jenis Diskon Kota

### Get List jenis Diskon Kota
Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/jenisdiskonkota?idprodukmix={value}&idpenanda={value}&tahunajaran={value}&page={value}&per_page={value}`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
                "c_IdDiskonKota": "number",
                "c_IdPenanda": "number",
                "c_StatusDK": "string",
                "c_Nilai": "string",
                "c_IdDiskon":"number",
                "c_TanggalAkhir": "string,date",
                "c_TanggalStart": "string,date",
                "c_IdJenisDiskon": "number",
                "c_InisialDiskon": "string",
                "c_IdBidangApprove": "number",
                "c_NamaDiskon": "string",
                "c_IsRelatif": "bolean",
                "c_PartDiskon": "bolean",
                "c_Prioritas": "number",
                "c_Kelompok":"string",
                "c_IsNeedDocument": "bolean",
                "c_Ikatan": "string",
                "c_Status":"string",
                "c_Updater": "string",
                "c_LastUpdate": "string,datetime",
                "c_Insert": "string,datetime",
                "c_NamaProdukMix": "string",
                "c_IdProdukMix": "number",
                "c_NamaBidang": "string",
                "c_Penanda": "string"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

### Get Data Produk MIX di DISKON
Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/jenisdiskonkota/produkmix`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
             {
            "c_IdProdukMix": "Number",
            "c_NamaProdukMix": "String"
        },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

### Get Data Produk di DISKON
Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/jenisdiskonkota/produkmix/{idprodukmix}`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
            "c_NamaProduk": "String"
        },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
