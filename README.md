# api Spak

## Opsi

### GET LIST MATA PELAJARAN

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
### GET DETAIL MATA PELAJARAN

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
### GET LIST KURIKULUM

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

### GET DETAIL KURIKULUM

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


### GET LIST BAB

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

### GET DETAIL BAB

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


### GET TAHUN AJARAN

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
### GET TAHUN AJARAN detail

Request :

- Method : GET
- Endpoint : `/api/v1/tahunAjaran/{id}`,
- Header : null
- Body : null

- Response :

```json
{
  "data": 
    {
      "id": "string, unique",
      "tahunAjaran": "string"
    }
  ,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


### GET TINGKAT KELAS

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
### GET TINGKAT KELAS detail

Request :

- Method : GET
- Endpoint : `/api/v1/tingkatkelas/{}`,
- Header : null
- Body : null

- Response :

```json
{
  "data": 
    {
      "id": "string, unique",
      "tingkatKelas": "string" // cth 12 SMA IPS
    }
  ,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


### GET Layanan/JENIS KELAS

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

### GET Layanan/JENIS KELAS Detail

Request :

- Method : GET
- Endpoint : `/api/v1/jenislayanan/{id}`,
- Header : null
- Body : null

- Response :

```json
{
  "data": 
    {
      "id": "string, unique",
      "jenisLayanan": "string"
    }
  ,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### GET KELOMPOK UJIAN

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

### GET KELOMPOK UJIAN Detail

Request :

- Method : GET
- Endpoint : `/api/v1/kelompokujian/{id}`,
- Header : null
- Body : null

- Response :

```json
{
  "data": 
    {
      "id": "string, unique",
      "nama": "string"
    }
  ,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### GET LIST SILABUS

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

### GET DETAIL SILABUS

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

### GET LIST MATA AJAR

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

### GET DETAIL MATA AJAR

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

### GET Peruntukan

Request :

- Method : GET
- Endpoint : `/api/v1/peruntukan`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
     {
            "id": "number",
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
### GET Peruntukan detail

Request :

- Method : GET
- Endpoint : `/api/v1/peruntukan/{id}`,
- Header : null
- Body : null

Response :

```json
{
  "data": 
     {
            "id": "number",
            "nama": "String"
        },

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```


### GET JENIS PRODUK

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
### GET JENIS PRODUK Detail

Request :

- Method : GET
- Endpoint : `/api/v1/jenis-produk/{id}`,
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
### GET List Enum Buku

Request :

- Method : GET
- Endpoint : `/api/v1/enumbuku`,
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
### GET  Enum Buku Detail

Request :

- Method : GET
- Endpoint : `/api/v1/enumbuku/{id}`,
- Header : null
- Body : null

Response :

```json
{
  "data": 
    {
      "idProduk": "string",
      "namaProduk": "string"
    },

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```



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

## Get Penanda Detail
Request :

- Method : GET
- Endpoint : `/api/v1/penanda/{id}`,
- Header : null
- Body : null

Response :

```json
{
  "data": 
     {
            "id": "int",
            "nama": "String"
        },

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
## Get Zona Detail
Request :

- Method : GET
- Endpoint : `/api/v1/zona/{id}`,
- Header : null
- Body : null

Response :

```json
{
  "data": 
     {
            "id": "int",
            "nama": "String"
        },
  

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
- Endpoint : `/api/v1/gedung?zona={idzona}&&keyword={value}`,
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

### get gedung by kota

Request

- Method : Get
- Endpoint : `api/v1/gokasir/list/gedung?kota={}`
- Body :


Response :

```json
{
  "data": [
    {
      "IdGedung": "825",
      "NamaGedung": "LETJEN. SUPRAPTO 22"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## Get Gedung Detail
Request :

- Method : GET
- Endpoint : `/api/v1/gedumg/{id}`,
- Header : null
- Body : null

Response :

```json
{
  "data": 
     {
            "id": "int",
            "nama": "String"
        },

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Get Jenis Paket
Request :

- Method : GET
- Endpoint : `/api/v1/jenisPaket`,
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
### Get kode paket
Request :

- Method : GET
- Endpoint : `/api/v1/jenisPaket/{idjenis}`,
- Header : null
- Body : null

Response :

```json
{
  "data": 
     {
            "id": "int",
            "nama": "String"
        },

  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
### get list bank

Request :

- Method : GET
- Endpoint : `/api/v1/list/bank?search=${nama}`

Response :

```json
{
  "data": [
        {
        "idbank": "string",
        "namabank": "string"
        }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
### get bank Detail

Request :

- Method : GET
- Endpoint : `/api/v1/list/bank/{id}`

Response :

```json
{
  "data": [
        {
        "idbank": "string",
        "namabank": "string"
        }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### get sekolah by kota dan jenjang pendidikan

Request

- Method : GET
- Endpoint : `api/v1/gokasir/list/sekolah?jenjangpendidikan={}&idkota={}`
- Body :

Response

```json
{
  "data": [
    {
      "IdSekolah": "number",
      "NamaSekolah": "String"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
### get sekolah detail

Request

- Method : GET
- Endpoint : `api/v1/gokasir/list/sekolah/id`
- Body :

Response

```json
{
  "data": 
    {
      "IdSekolah": "number",
      "NamaSekolah": "String"
    }
  ,
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
## BARU 
### get jenis sekolah 

Request

- Method : GET
- Endpoint : `api/v1/gokasir/list/jenissekolah` 
- Body :

Response

```json
{
  "data": [
    {
      "IdjenisSekolah": "number",
      "NamaSekolah": "String"
    }],//"SD","MI","SMP","MTS","SMA","MA","SMK","PONPES","ALUMNI"
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
### get jenis sekolah  detail

Request

- Method : GET
- Endpoint : `api/v1/gokasir/list/jenissekolah/id` 
- Body :

Response

```json
{
  "data": 
    {
      "IdjenisSekolah": "number",
      "NamaSekolah": "String"
    },//"SD","MI","SMP","MTS","SMA","MA","SMK","PONPES","ALUMNI"
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Get Kelas

Request

- Method : GET
- Endpoint : `api/v1/gokasir/list/kelas` 
- Body :

Response

```json
{
  "data": [
      {
            "c_IdKelas": "number",
            "c_NamaKelas": "String"
        }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
### Get Kelas detail

Request

- Method : GET
- Endpoint : `api/v1/gokasir/list/kelas/{id}` 
- Body :

Response

```json
{
  "data": {
            "c_IdKelas": "number",
            "c_NamaKelas": "String"
        },
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### Get list Metode


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

### get kewilayahan by kota

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
      "IdKewilayahan": "number",
      "NamaKewilayahan": "String"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
### get kewilayahan detail

Request :

- Method : get
- Endpoint : `api/v1/gokasir/list/kewilayahanbykota/{id}`
- Body :



Response :

```json
{
  "data": 
    {
      "IdKewilayahan": "number",
      "NamaKewilayahan": "String"
    },
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### get komar

Request :

- Method : get
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
      "IdKomar": "number",
      "NamaKomar": "String"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```
### get komar detail

Request :

- Method : Get
- Endpoint : `api/v1/gokasir/list/komar/{id}`
- Body :


Response :

```json
{
  "data": [
    {
      "IdKomar": "number",
      "NamaKomar": "String"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```