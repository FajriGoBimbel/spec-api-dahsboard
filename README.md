# API Spec

## Get Gedung by id kota

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/gedung?idkota={value}&&keyword={value}`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
                "c_IdGedung": "int",
                "c_NamaGedung": "String"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
## Get Gedung by id kota

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/penagihan/penagihanpusat?gedung={value}&kelas={value}&tahunajaran={value}&tingkat={value}&page={value}&per_page={value}`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
            "c_Penanda": "String",
            "c_NamaGedung": "String",
            "c_IdPembelian": "int",
            "c_NoRegistrasi": "String",
            "c_NamaLengkap": "String",
            "c_IdKelas": "int",
            "c_NamaKelas": "String",
            "c_NamaBundling": "String",
            "c_Telp": "String",
            "c_TelpOrtu": "String",
            "c_KewajibanBayar": "int",
            "c_TotalBayar": "int",
            "c_StatusBayar": "int",
            "c_Tglterakhirbayar": "String, date",
            "c_totalbyr_tempo": "String", //contoh "1600000;2023-09-13",
            "c_CicilanTerbayar": "int",
            "c_Sisa": "Int",
            "c_JatuhTempoTerdekat": "String, date",
            "c_Jatuhtempoberikutnya": "String, date",
            "c_Tagihanberikutnya": "int",
            "c_IsJatuhTempo": "bolean"
        },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```

