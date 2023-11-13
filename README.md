# API Spec

## Akses Role

### get list mata pelajaran

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

### get list bab

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

### get list tree bab

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

### get list soal

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
