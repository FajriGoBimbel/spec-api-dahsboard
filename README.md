# API Spec

## Auth

### Registrasi

#### Registrasi Akun

Request :
- Method : POST
- Endpoint : `/api/v1/register`
- Header : null
- Body :

```json 
{
    "nama_lengkap" : "string",
    "nohp": "number",
    "email" : "string",
    "password" : "string",
    "password_confirm" : "string"
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

### Login

#### Login Tamu

Request :
- Method : POST
- Endpoint : `/api/v1/login-tamu`
- Header : null
- Body :

```json 
{
    "email" : "string",
    "password" : "string",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "kelas_detail": {
            "id": "string, unique",
            "tingkat_kelas": "string",
            "jurusan": "string",
            "kelompok_sekolah": "string", 
         },
         "id_kurikulum": "number",
         "kurikulum_detail": {
            "id": "string, unique",
            "nama_kurilkulum": "string",
            "inisial_kurikulum": "string",
            "tahun_terbit": "number"
         },
         "daftar_produk_teaser": [
            {
                "id_komponent_produk": "string, unique",
                "id_bundling": "string, unique",
                "nama_bundling": "string",
                "nama_produk": "string",
                "id_jenis_produk": "string, unique",,
                "nama_jenis_produk": "string",
                "tanggal_awal": "date",
                "tanggal_akhir": "date",
                "id_sekolah_kelas": "string, unique",
            },
        ],
         "status": "enum",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```