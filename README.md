# API Spec

# Module Go Produk

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

### Create Jenis Diskon Kota

Request :

- Method : POST
- Endpoint : `/api/v1/goproduk/jenisdiskonkota`,
- Header : null
- Body :
```json
{
  "IdJenisDiskon": "number",
  "nilai":  "number",
  "tanggalawal":  "string,date",
  "tanggalakhir":  "string,date",
  "tahunajaran": "String",
  "penanda": ["number"],
  "produkmix":  ["number"]
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

### Delete Jenis Diskon Kota

Request :

- Method : DELETE
- Endpoint : `/api/v1/goproduk/jenisdiskonkota/idjenisdiskonkota`,
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

### Ajukan jenis Diskon Kota 

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/jenisdiskonkota/ajukan`,
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

### Validasi Jenis Diskon Kota

Request :

- Method : PUT
- Endpoint : `/api/v1/goproduk/jenisdiskonkota/{idjenisdiskonKota}`,
- Header : null
- Body :
```json
{ 
    "idjenisdiskonkota":"number",
    "Status":"bolean",
    "user_id" :"String"
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

## bundling

### get list bundling
Request :

- Method : get
- Endpoint : `/api/v1/goproduk/bundling?page={value}&per_page={value}&tingkatkelas={value}&kota={value}&tahunajaran={value}`,
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

### gek Kota Bundling
Request :

- Method : get
- Endpoint : `/api/v1/goproduk/bundling/kotabundling/{idprodukmix}`,
- Header : null
- Body :
Response :

```json
    {
        "data": [
             {
            "c_IdPenanda": "Number",
            "c_NamaPenanda": "String"
        }
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

### gek Kota Bundling
Request :

- Method : get
- Endpoint : `/api/v1/goproduk/bundling/KomponenProduk/{idbundling}`,
- Header : null
- Body :
Response :

```json
    {
        "data": [
              {
                "c_IdPemberlakuan": "number",
                "c_IdBundling": "number",
                "c_IdProduk": "number",
                "c_NamaProduk": "String",
                "c_Keterangan": "String",
                "c_HPPProduk": "number",
                "c_Penambahanharga": "number",
                "c_Harga": "number"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```