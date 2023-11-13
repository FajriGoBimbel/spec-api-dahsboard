# API Spec

## Jenis Produk

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

## Kelompok Ujian

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

## Kode Paket

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

## Kunci Jawaban

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
