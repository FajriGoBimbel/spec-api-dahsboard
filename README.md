# API Spec

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
