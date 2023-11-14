# API Spec

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

>**NOTE**
>Tidak ada di gokasir existing.
>
>Ex :
>
>##### GET METODE
>  - Kartu debit
>  - Kartu kredit
>  - transfer
>##### GET JENIS
>  - Antar Rekening
>  - Payment Gateway
>  - Virtual Account
>#### GET TIPE 
>  - NOMINAL
>  - PERSEN

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