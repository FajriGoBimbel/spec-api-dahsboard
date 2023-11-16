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
        "data":[
             {
                "c_IdPenanda": "number",
                "c_Penanda": "BANDUNG",
                "c_IdBundling": "number",
                "c_NamaBundling": "string",
                "NamaBundling": "string",
                "c_IdProdukMix": "number",
                "c_NamaProdukMix": "string",
                "c_IsOnline": "bolean",
                "c_IsKerjaSama": "bolean",
                "c_TahunAjaran": "string",
                "c_Status": "string",
                "c_IdSekolahKelas": "number",
                "c_TingkatKelas": "string",
                "c_JenisKelas": "string",
                "c_TanggalAwal": "string,date",
                "c_TanggalAkhir": "string,date",
                "c_HargaPT": "number",
                "c_HargaFasilitas": "number",
                "c_Deskripsi": "string",
                "c_JenisBiayaOperasional": "number",
                "c_KapasitasMax": "number",
                "c_BiayaOperasional": "number",
                "c_HargaSebelum": "number",
                "c_HargaPenyesuaian": "number",
                "c_HargaTotal": "number",
                "c_Margin": "number",
                "c_BiayaTercantum": "number",
                "c_IdPola": "number",
                "c_Pola": "string",
                "c_SkemaCicilan": "{\"1\": 50, \"2\": 30, \"3\": 20}",
                "c_IsTeaser": "bolean",
                "c_IsJaminan100": "bolean",
                "c_IsJaminan100Txt": "bolean",
                "c_Action": "string"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
 {
            "c_IdPenanda": "1",
            "c_Penanda": "BANDUNG",
            "c_IdSekolahKelas": "9",
            "c_TingkatKelas": "9 SMP UMUM",
            "c_IdBundling": "1226963",
            "c_NamaBundling": " TWT 9 SMP UMUM Privat Non Primetime 25P K13R 23/24",
            "NamaBundling": "1226963 -  TWT 9 SMP UMUM Privat Non Primetime 25P K13R 23/24",
            "c_IdProdukMix": "13115",
            "c_NamaProdukMix": "9-SMP-UMUM-PRV-252525-N-K13R-T-11B5",
            "c_TahunAjaran": "2023/2024",
            "c_JenisKelas": "PRIVAT",
            "c_TanggalAwal": "2023-11-07",
            "c_TanggalAkhir": "2023-11-07",
            "c_Deskripsi": "TWT 9 SMP UMUM Privat Non Primetime 25P K13R 23/24\n",
            "c_HargaPT": "0",
            "c_HargaFasilitas": "524025",
            "c_BiayaOperasional": "0",
            "c_HargaTotal": "6750000",
            "c_IsOnline": "N",
            "c_IsKerjaSama": "N",
            "c_IsJaminan100": "0",
            "c_IsJaminan100Txt": "N",
            "c_Status": "Aktif",
            "c_IsPenyesuaian": " ( Penyesuaian )"
        },
### get Kota Bundling
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

### get Komponen Produk
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

### get List Bundling
Request :

- Method : get
- Endpoint : `/api/v1/goproduk/bundling/list`,
- Header : null
- Body :
Response :

```json
    {
        "data": [
                 {
                    "c_IdPenanda": "number",
                    "c_Penanda": "string",
                    "c_IdSekolahKelas": "number",
                    "c_TingkatKelas": "string",
                    "c_IdBundling": "number",
                    "c_NamaBundling": "string",
                    "NamaBundling": "string",
                    "c_IdProdukMix": "number",
                    "c_NamaProdukMix": "string",
                    "c_TahunAjaran": "string",
                    "c_JenisKelas": "string",
                    "c_TanggalAwal": "string,date",
                    "c_TanggalAkhir": "string,date",
                    "c_Deskripsi": "string",
                    "c_HargaPT": "number",
                    "c_HargaFasilitas": "number",
                    "c_BiayaOperasional":"number",
                    "c_HargaTotal": "number",
                    "c_IsOnline": "bolean",
                    "c_IsKerjaSama": "bolean",
                    "c_IsJaminan100": "bolean",
                    "c_IsJaminan100Txt": "String",
                    "c_Status": "string",
                    "c_IsPenyesuaian": "bolean",
                }
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

### Get list Bundling di membuat

Request :

- Method : get
- Endpoint : `/api/v1/goproduk/bundling`,
- Header : null
- Body :
Response :

```json
    {
        "data": [
                {
                    "c_IdPenanda": "number",
                    "c_Penanda": "string",
                    "c_IdBundling": "number",
                    "c_NamaBundling": "string",
                    "NamaBundling": "string",
                    "c_IdProdukMix": "number",
                    "c_NamaProdukMix": "string",
                    "c_IsOnline": "N",
                    "c_IsKerjaSama": "N",
                    "c_TahunAjaran": "string",
                    "c_Status":"string",
                    "c_IdSekolahKelas": "number",
                    "c_TingkatKelas": "string",
                    "c_JenisKelas": "string",
                    "c_TanggalAwal": "string,date",
                    "c_TanggalAkhir": "string,date",
                    "c_HargaPT": "number",
                    "c_HargaFasilitas": "number",
                    "c_Deskripsi": "string",
                    "c_JenisBiayaOperasional": "string",
                    "c_KapasitasMax": "number",
                    "c_BiayaOperasional": "number",
                    "c_HargaSebelum": "number",
                    "c_HargaPenyesuaian":"number",
                    "c_HargaTotal": "number",
                    "c_Margin": "number",
                    "c_BiayaTercantum": "number",
                    "c_IdPola": "number",
                    "c_Pola": "string",
                    "c_SkemaCicilan":[
                        {
                            "cicilan-ke":"number",
                            "jumlah_pembayaran":"number"//dalam persen misal 20 berarti 20 persen
                        }
                    ],
                    "c_IsTeaser":"bolean",
                    "c_IsJaminan100": "bolean",
                    "c_IsJaminan100Txt": "bolean",
                    "c_Action": "string"
                },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
### Get List Produk mix di dalam pembuatan bundling
Request :

- Method : get
- Endpoint : `/api/v1/goproduk/bundling/produkmix?iskerjasama={value}&jenislayanan={value}&tingkatkelas={value}`,
- Header : null
- Body :
Response :

```json
    {
        "data": [
                {
            "c_IdProdukMix": "number",
            "c_NamaProdukMix": "string"
        },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

### get isi bundling
Request :

- Method : get
- Endpoint : `/api/v1/goproduk/bundling/isi/{idbundling}`,
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
                    "c_NamaProduk": "string",
                    "c_HPPProduk": "number",
                    "c_Index": "string",
                    "c_Jumlah": "number",
                    "c_Penambahanharga": "number",
                    "c_TanggalPemberian": "string,date",
                    "c_TanggalAkhirPemberian": "string,date",
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


### create bundling


Request :

- Method : Post
- Endpoint : `/api/v1/goproduk/bundling`,
- Header : null
- Body :
```json
        {
        "idprodukmix": "number",
        "kota": "number",
        "jenislayanan": "number",
        "tingkatkelas": "number",
        "iskerjasama": "bolean",
        "isonline": "bolean",
        "namabundling": "string",
        "tglawaljual": "string,date",
        "tglakhirjual": "string,date",
        "deskripsi": "string",
        "isjaminan100": "bolean",
        "hargapt": "number",
        "biayaoperasional": "number",
        "tahunajaran": "String",
        "jenisbiayaoperasional": {
            "biayaoperasionallistrik": "number",
            "biayainternet": "number",
            "biayazoom": "number",
            "transportpengajar": "number",
            "uangmakanpengajar": "number",
            "biayaoperasionalsekolah": "number"
        },
        "polacicilan": "number",
        "isteaser": "bolean",
        "isperpanjang": "bolean"
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


### Edit bundling


Request :

- Method : Put
- Endpoint : `/api/v1/goproduk/bundling`,
- Header : null
- Body :
```json
        {
        "idbundling":"number",
        "idprodukmix": "number",
        "kota": "number",
        "jenislayanan": "number",
        "tingkatkelas": "number",
        "iskerjasama": "bolean",
        "isonline": "bolean",
        "namabundling": "string",
        "tglawaljual": "string,date",
        "tglakhirjual": "string,date",
        "deskripsi": "string",
        "isjaminan100": "bolean",
        "hargapt": "number",
        "biayaoperasional": "number",
        "tahunajaran": "String",
        "jenisbiayaoperasional": {
            "biayaoperasionallistrik": "number",
            "biayainternet": "number",
            "biayazoom": "number",
            "transportpengajar": "number",
            "uangmakanpengajar": "number",
            "biayaoperasionalsekolah": "number"
        },
        "polacicilan": "number",
        "isteaser": "bolean",
        "isperpanjang": "bolean"
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
### Edit Margin bundling


Request :

- Method : Put
- Endpoint : `/api/v1/goproduk/bundling/margin`,
- Header : null
- Body :
```json
     {
        "idbundling": "number",
        "margin": "number",
        "biayatercantum": "number"
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

### Delete bundling


Request :

- Method : DELETE
- Endpoint : `/api/v1/goproduk/bundling/{idbundling}`,
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

### Penytesuaian Harga bundling

Request :

- Method : Put
- Endpoint : `/api/v1/goproduk/bundling/penyesuaian`,
- Header : null
- Body :
```json
        {
        "idbundling":"number",
        "penyesuaianHarga":"number"
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
### update Status bundling

Request :

- Method : Put
- Endpoint : `/api/v1/goproduk/bundling/pengajuan`,
- Header : null
- Body :
```json
        {
        "idbundling":"number",
        "status":"String"
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
## verifikasi

### Get Kota produk mix

Request :

- Method : Get
- Endpoint : `/api/v1/goproduk/bundling/verifikasi/kota/{idprodukmix}`,
- Header : null
- Body :
Response :

```json
    {
        "data": [
                {
                "c_IdPenanda": "number",
                "c_NamaPenanda": "string"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
### Get Komponen produk

Request :

- Method : Get
- Endpoint : `/api/v1/goproduk/bundling/verifikasi/komponenProduk/{idbundling}`,
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
                    "c_NamaProduk": "string",
                    "c_Keterangan": "string",
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

### verifikasi bundling

Request :

- Method : post
- Endpoint : `/api/v1/goproduk/bundling/verifikasi`,
- Header : null
- Body :
```json
{
    "idbundling":"number",
    "user_id": "string",
    "status": "string"
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


### pengesahan bundling

Request :

- Method : post
- Endpoint : `/api/v1/goproduk/bundling/pengesahan`,
- Header : null
- Body :
```json
{
    "idbundling":"number",
    "user_id": "string",
    "status": "string"
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

## pemberlakuan Produk

### get list Pemberlakuan Produk by tahun ajaran dan kota

Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/pemberlakuan?tahunajaran={value}&kota={}&page={}&per_page={}`,
- Header : null
- Body :

Response :

```json
    {
        "data":[
             {
                "idprodukasli": "number",
                "idProdukPP": "number",
                "c_NamaProduk": "String",
                "c_Kurikulum": "string",
                "c_NamaTingkatKelas": "string",
                "c_JenisKelas": "string",
                "c_NamaBidang": "string",
                "c_HPP": "number",
                "c_OngkosKirim": "number",
                "c_Status": "number",
                "c_Penanda": "number",
                "c_NamaJenisProduk": "string"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

### get list Pemberlakuan Produk

Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/pemberlakuan?jenisproduk={value}&page={}&per_page={}`,
- Header : null
- Body :

Response :

```json
    {
        "data":[
             {
                "idprodukasli": "number",
                "idProdukPP": "number",
                "c_NamaProduk": "String",
                "c_Kurikulum": "string",
                "c_NamaTingkatKelas": "string",
                "c_JenisKelas": "string",
                "c_NamaBidang": "string",
                "c_HPP": "number",
                "c_OngkosKirim": "number",
                "c_Status": "number",
                "c_Penanda": "number",
                "c_NamaJenisProduk": "string"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
### create Pemberlakuan Produk

Request :

- Method : POST
- Endpoint : `/api/v1/goproduk/pemberlakuan `,
- Header : null
- Body :
```json
        {
            "idproduk": 37963,
            "idpenanda": "194",
            "tp": "2023/2024",
            "hpp": 200000,
            "status": "Create",
            "ongkos": "N",
            "beban": "SISWA"
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

### Get list Siap Kirim
Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/pemberlakuan/kirim`,
- Header : null
- Body :

Response :

```json
    {
        "data":[
             {
            "c_NamaProduk": "string",
            "c_HPP": "number",
            "c_OngkosKirim": "Bolean",
            "c_Status": "string",
            "c_IdPemberlakuan": "number",
            "cek": "bolean"
        },

        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

### kirim Pemberlakuan Produk

Request :

- Method : put
- Endpoint : `/api/v1/goproduk/pemberlakuan/kirim`,
- Header : null
- Body :
```json
    {
         [
            {
                
                "c_IdPemberlakuan": "number",
                "c_idPenanda":"number"
                },

        ]
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
### get list pemberlakuan persetujuan

Request :

- Method : GET
- Endpoint : `/api/v1/goproduk/pemberlakuan/validasi?jenisproduk={value}&page={}&per_page={}`,
- Header : null
- Body :

Response :

```json
    {
        "data":[
            {
            "c_IdPemberlakuan": "number",
            "c_TahunAjaran": "string",
            "c_HPP": "number",
            "c_Status": "string",
            "c_NamaProduk":"string",
            "c_Penanda": "string",
            "c_OngkosKirim": "bolean",
            "cek": "bolean"
            }
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
