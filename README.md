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

## PETUGAS

### TAMBAH PETUGAS

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

### EDIT PETUGAS

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

### GET LIST PETUGAS

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

### Verivikasi 
masih Menunggu untuk bisa verifikasi


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

#### get isi Buku


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

