# API Spec

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

## Transaksi Artikel

### Simulasi Artikel

#### Get DataTabel Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/transaksi-artikel/simulasi/datatabel?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?tgl_awal={value}?tgl_akhir={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "nomorInvoice": "0093230923143303",
            "tanggalDatang": "2023-09-23",
            "idGedungDatang": "unique",
            "noRegistrasi": "number",
            "namaLengkap": "string",
            "hp": "number",
            "idSekolah": "unique",
            "jenjangPendidikan": "string",
            "idGedungBelajar": "unique",
            "tahunAjaran": "string",
            "idSekolahKelas": "unique",
            "namaSekolahKelas": "string",
            "idKelas": "unique",
            "caraBayar": "",
            "idBundling": "unique",
            "namaBundling": "string",
            "hargaPT": "number",
            "hargaJual": "number",
            "totalBayar": "number",
            "kodeUnik": "unique",
            "nomorVA": "number",
            "tanggalExpired": "2023-09-30",
            "nominalBayar": "number",
            "tanggalDigunakan": null,
            "status": "enum",
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

#### Get Biodata untuk Tambah Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata?nama_lengkap={value}?tgl_lahir={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "NoRegistrasi": "unique",
          "NamaLengkap": "string",
          "JenisKelamin": "enum",
          "TanggalLahir": "2006-10-14",
          "alamat": "string",
          "tlp": "number",
          "hp": "number",
          "hp2": "number",
          "email": "jasminechrisna14@gmail.com",
          "email2": "jasminechrisna14@gmail.com",
          "agama": "enum",
          "ibuKandung": "string",
          "isSiswa": "boolean",
          "status": "enum"  
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Get Biodata Detail => Info siswa Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "noregistrasi": "unique",
          "namalengkap": "string",
          "namapanggilan": "string",
          "provinsikelahiran": "unique",
          "namaprovinsikelahiran": "string",
          "kotakelahiran": "unique",
          "namakotakelahiran": "string",
          "jeniskelamin": "enum",
          "tanggallahir": "2006-10-14",
          "namaibukandung": "string",
          "pekerjaanortu": "string",
          "agama": "enum",
          "golongandarah": null,
          "alamat": "Perumahan Griya Asri 2, Jl. Flamboyan Blok J26 no.48 Rt 08/Rw 40 \n",
          "provinsialamat": "12",
          "namaprovinsialamat": "PROVINSI JAWA BARAT",
          "kotaalamat": "156",
          "namakotaalamat": "KABUPATEN BEKASI",
          "kecamatanalamat": "313",
          "kelurahan": "2664",
          "kodepos": "17510",
          "statuskepemilikan": null,
          "notlp": null,
          "nohpsiswa": "089613312329",
          "nohportu": "081213009680",
          "emailsiswa": "jihanoktavia14@gmail.com",
          "emailortu": "sn418103@gmail.com",
          "status": "Aktif",
          "hubungan": "Ayah"  
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Get Biodata Detail => Kartu Identitas Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/kartu-identitas?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "idIdentitas": "55234",
          "jenisKartuIdentitas": "KTP",
          "image_kartu_identitas": "string",
          "idProvinsi": "1",
          "provinsi": "PROVINSI ACEH",
          "idKota": "1",
          "kota": "KABUPATEN ACEH BARAT"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Get Biodata Detail => Saudara Simulasi Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/saudara?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "idBiodataSaudara": "529",
          "noRegistrasi": "61014004401",
          "hubungan": "KAKAK",
          "nama": "jamal",
          "tanggalLahir": "2023-11-14",
          "umur": "0 Thn"  
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Update Biodata => info Biodata

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "noregistrasi": "unique",
          "namalengkap": "string",
          "namapanggilan": "string",
          "provinsikelahiran": "unique",
          "namaprovinsikelahiran": "string",
          "kotakelahiran": "unique",
          "namakotakelahiran": "string",
          "jeniskelamin": "enum",
          "tanggallahir": "2006-10-14",
          "namaibukandung": "string",
          "pekerjaanortu": "string",
          "agama": "enum",
          "golongandarah": null,
          "alamat": "Perumahan Griya Asri 2, Jl. Flamboyan Blok J26 no.48 Rt 08/Rw 40 \n",
          "provinsialamat": "12",
          "namaprovinsialamat": "PROVINSI JAWA BARAT",
          "kotaalamat": "156",
          "namakotaalamat": "KABUPATEN BEKASI",
          "kecamatanalamat": "313",
          "kelurahan": "2664",
          "kodepos": "17510",
          "statuskepemilikan": null,
          "notlp": null,
          "nohpsiswa": "089613312329",
          "nohportu": "081213009680",
          "emailsiswa": "jihanoktavia14@gmail.com",
          "emailortu": "sn418103@gmail.com",
          "status": "Aktif",
          "hubungan": "Ayah"
        }
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Update Biodata => Kartu Identitas

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/kartu-identitas?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "jenis_kartu_identitas": "string",
          "idprovinsi": "unique",
          "idkota": "unique", //generate dari tanggal lahir
          "image_kartu_identitas": "string"
        }
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Update Biodata => Saudara

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/saudara?no_register={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "nama": "string",
          "tanggallahir": "2006-10-14",
          "umur": "number", //generate dari tanggal lahir
          "hubungan": "Ayah"
        }
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```

#### Delete Biodata => Saudara

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/saudara?no_register={value}?id_identitas={value}`,
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

#### Delete Biodata => Kartu Identitas

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/simulasi-artikel/biodata/detail/kartu-identitas?no_register={value}?id_saudara={value}`,
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


### Pembayaran Artikel

#### Get Data Invoice Pembayaran Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/pembayaran-artikel/invoice?no_invoice={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "nomorInvoice": "0002231003103926",
          "tanggalDatang": "2023-10-03",
          "idGedungDatang": "1147",
          "noRegistrasi": "051231114789",
          "namaLengkap": "uji coba keuangan",
          "hp": "08112385459",
          "hpOrtu": "08112385459",
          "email": "tiaraayunda373@gmai.com",
          "emailOrtu": "tiara@gmail.com",
          "idSekolah": "392716",
          "namaSekolah": "HOMESCHOOLING MILENIAL UNGGUL",
          "jenjangPendidikan": "SMA",
          "idGedungBelajar": "2",
          "tahunAjaran": "2023/2024",
          "idSekolahKelas": "14",
          "namaSekolahKelas": "12 SMA IPA",
          "idKelas": "269738",
          "caraBayar": "",
          "jenisBayar": "",
          "idBundling": "766519",
          "namaBundling": "TWT 12 SMA IPA K13R 4P 23/24",
          "produk": {
              "data": [
                  {
                      "id": 32664,
                      "nama": "23_e- Buku Sakti Empati Mandiri 12 SMA IPA K13R"
                  },
              ],
              "hargapt": 200000,
              "hargajual": 9500000,
              "hargaproduk": 9700000
          },
          "c_Diskon": {
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
          "totalBayar": "9700000",
          "kodeUnik": "0",
          "totalYangDiBayarkan": "9700000",
          "skemaCicilan": [
              {
                  "jumlah": 200000,
                  "cicilanke": 0,
                  "jumlahacc": 200000,
                  "jatuhtempo": "2023-10-03",
                  "keterangan": "Pendaftaran"
              },
          ],
          "idPola": "number",
          "polaCicilan": {
              "1": 50,
              "2": 30,
              "3": 20
          },
          "tanggalExpired": "2023-10-10",
          "status": "enum",
          "idPembelian": "unique",
          "hargaSebelum": "number",
          "hargaPenyesuaian": "number"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```


#### Get Datatabel Nomor Invoice Pembayaran Artikel

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/pembayaran-artikel/invoice/no_invoice?tanggal={value}?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}`,
- Header : null
- Body : null

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


## Dokument Diskon

### Unggah Dokument Diskon

#### Get DataTabel Unggah Dokument Diskon

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/unggah/datatabel?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?tingkat_kelas={value}?kota={value}?gedung={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "idPembelian": "unique",
            "namaGedung": "PW 36-B",
            "noRegistrasi": "060514000201",
            "nomorInvoice": "0002231003161146",
            "namaLengkap": "ADELYA SELFI LISYANA",
            "namaKelas": "12-IPS-R-N-102",
            "namaBundling": "TWT 12 SMA IPS K13R 4P 23/24",
            "statusAjuan": "enum",
            "tglbayarpertama": "2023-10-03",
            "lamabayarpertama": 42,
            "tanggalTerakhirUnggah": "-",
            "action": "Lihat Ajuan",
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


#### Get Diskon Unggah Dokument Diskon

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/unggah/diskon?id_pembelian={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "idAmbilDiskon": "unique",
          "ajuanDiskon": "Diskon Pemuda 5%_",
          "keterangan": "string",
          "isNeedDocument": "boolean",
          "tanggalUnggah": null,
          "dokumenDiskon": null,
          "status": "enum"
        },
    ],

    "meta": {
        "code": "number",
        "message": "string",
        "status": "string"
    }
}
```


### Validasi Dokument Diskon

#### Get DataTabel Validasi Dokument Diskon

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/validasi/datatabel?keyword={value}?page={value}?page_count={value}?per_page={value}?total_count={value}?sort={value}?order_by={value}?tahun_ajaran={value}?tingkat_kelas={value}?kota={value}?gedung={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
            "idPembelian": "unique",
            "namaGedung": "PW 36-B",
            "noRegistrasi": "060514000201",
            "nomorInvoice": "0002231003161146",
            "namaLengkap": "ADELYA SELFI LISYANA",
            "namaKelas": "12-IPS-R-N-102",
            "namaBundling": "TWT 12 SMA IPS K13R 4P 23/24",
            "statusAjuan": "enum",
            "tglbayarpertama": "2023-10-03",
            "lamabayarpertama": 42,
            "tanggalTerakhirUnggah": "-",
            "action": "Lihat Ajuan",
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


#### Get Detail Validasi Dokument Diskon (Skema Pembayaran)

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/validasi/detail?id={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "id": "8711535",
          "jumlah": "200000",
          "keterangan": "PENDF.",
          "cicilanke": "0",
          "jatuhtempo": "2023-06-07",
          "sudahbayar": "200000",
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


#### Get Detail Validasi Dokument Diskon (Diskon)

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/dokument-diskon/validasi/diskon?id={value}`,
- Header : null
- Body : null

Response :

```json
{
  "data": [
        {
          "idJenisDiskon": "unique",
            "idAmbilDiskon": "unique",
            "idDiskonKeluarkan": "unique",
            "isSyarat": "boolean",
            "isPart": "boolean",
            "diskonPersen": null,
            "isRelatif": "boolean",
            "diskonRP": "49999",
            "diskonRPAsli": "49999",
            "namaReferensi": "",
            "filePrasyarat": [],
            "status": "ACC",
            "statusAsli": "Aktif",
            "namaDiskon": "Diskon TOBK Promosi 100%_",
            "isACC": "1",
            "tanggalUnggah": null,
            "isACCASli": "1"
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


## BASTUP

### TAMBAH DATA BASTUP

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/bastup`
- Header : null
- Body :

```json
{
  "nomorBastup": "string",
  "tanggalTerimaUang": "string",
  "yangMenyerahkan": "string",
  "fileDokumen": "string"
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

### GET DATA TABLE LIST BASTUP

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastup/${params.tanggalAwal}/${params.tanggalAkhir}/${params.status}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "NoBASTUP": "string",
      "TanggalTerima": "date and time",
      "NIKPenyetor": "string",
      "NamaPenyetor": "string",
      "NIKPenerima": "string",
      "NamaPenerima": "string",
      "NamaFile": "string",
      "Status": "string",
      "Jumlah": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

### UBAH BASTUP

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/bastup`
- Header : null
- Body :

```json
{
  "nomorBastup": "string",
  "tanggalTerimaUang": "string",
  "yangMenyerahkan": "string",
  "fileDokumen": "string"
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

### GET DATA LIST SISWA BASTUP

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/siswabastup`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string, unique",
      "namaSiswa": "string",
      "jumlah": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### TAMBAH SISWA BERDASARKAN KODE BASTUP

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/siswabastup`
- Header : null
- Body :

```json
{
  "nomorBastup": "string",
  "namaSiswa": "string",
  "jumlahUang": "number"
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

### UPDATE STATUS LENGKAP dan TIDAK LENGKAP

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/bastup/status/${params.kodeBastup}`
- Header : null
- Body :

```json
{
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

### KIRIM DATA BASTUP

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/bastup/${params.kodeBastup}`
- Header : null
- Body :

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

### DELETE DATA BASTUP

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/bastup/${params.id}`
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

### GET DATA TABLE VALIDASI BASTUP

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastup/${params.tanggalAwal}/${params.tanggalAkhir}/${params.status}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "NoBASTUP": "string",
      "TanggalTerima": "date and time",
      "NIKPenyetor": "string",
      "NamaPenyetor": "string",
      "NIKPenerima": "string",
      "NamaPenerima": "string",
      "NamaFile": "string",
      "Status": "string",
      "Jumlah": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

### UPDATE APPROVE BASTUP

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/bastup/${params.id}`
- Header : null
- Body :

```json
{
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

## BASTPH

### TAMBAH DATA BASTPH

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/bastph`
- Header : null
- Body :

```json
{
  "nomorBashtph": "string",
  "tanggalSerahTerima": "string",
  "waktuSetoran": "string",
  "jumlahCash": "number",
  "penerimaSetoran": "string"
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

### GET DATA TABLE TRANSAKSI BASTUP

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastup/transaksi/${params.tanggalAwal}/${params.tanggalAkhir}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "namaBundling": "string",
      "noKwitansi": "string",
      "noBastup": "string",
      "tanggalTransaksi": "string",
      "jumlahCash": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

### GET DATA TABLE BASTPH

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastph/${params.tanggalAwal}/${params.tanggalAkhir}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "nomorBastph": "string",
      "tanggalSerahTerima": "date and time",
      "penerimaSetoran": "string",
      "jenisSetoran": "string",
      "jumlahCash": "string",
      "status": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

### DELETE DATA BASTPH

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/bastph/${params.id}`
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

### KIRIM DATA BASTPH

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/bastph/${params.kodeBastph}`
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

### GET DATA TABLE LIST VALIDASI BASHTPH

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/bastph/${params.tanggalAwal}/${params.tanggalAkhir}/${params.status}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "id": "string,unique",
      "NoBASTPH": "string",
      "TanggalSerahTerima": "date and time",
      "NIKPenerima": "string",
      "NamaPenerima": "string",
      "Status": "string",
      "JumlahPenerimaan": "string",
      "JenisWaktuPenerimaan": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

## LSPH

### TAMBAH DATA LSPH

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/lsph`
- Header : null
- Body :

```json
{
  "nomorLsph": "string", // auto generated
  "namaBank": "string",
  "noRekening": "string",
  "tanggalSetor": "date and time"
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

### GET LIST BANK

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/banks`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "IdBank": "string",
      "NamaBank": "string"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

### GET ISI BASTPH BY KODE LPH

Request :

- Method : GET
- Endpoint : `/api/v1/gokasir/lph/${params.kodeLph}`
- Header : null
- Body : null

Response :

```json
{
  "data": [
    {
      "NoBASTPH": "string",
      "TanggalSerahTerima": "date and time",
      "JenisWaktuPenerimaan": "string",
      "NIKPenyetor": "string",
      "NamaPenyetor": "string",
      "Status": "string",
      "JumlahPenerimaan": "mumber",
      "JumlahSetor": "number",
      "SisaSetor": "number",
      "RencanaSetor": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string",
    "total_count": "number",
    "page_count": "number",
    "page": "number",
    "per_page": "number",
    "sort": "",
    "order_by": "created_at",
    "keyword": ""
  }
}
```

### TAMBAH RENCANA SETORAN BY KODE LSPH

Request :

- Method : POST
- Endpoint : `/api/v1/gokasir/lsph/setsetoran/${params.kodeLsph}`
- Header : null
- Body :

```json
{
  "nomorBastph": "string",
  "sisaSetor": "number",
  "rencanaSetor": "number"
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

### KIRIM STATUS LSPH

Request :

- Method : PUT
- Endpoint : `/api/v1/gokasir/lsph/status/${params.kodeLsph}`
- Header : null
- Body :

```json
{
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

### DELETE DATA LSPH

Request :

- Method : DELETE
- Endpoint : `/api/v1/gokasir/lsph/${params.kodeLsph}`
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

> **NOTE**
> Tidak ada di gokasir existing.
>
> Ex :
>
> ##### GET METODE
>
> - Kartu debit
> - Kartu kredit
> - transfer
>
> ##### GET JENIS
>
> - Antar Rekening
> - Payment Gateway
> - Virtual Account
>
> #### GET TIPE
>
> - NOMINAL
> - PERSEN

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

> **_NOTE:_** hanya prediksi, belum di coba di gokasir existing.

### add list mdr

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/mdr/add`
- Body :

```json
{
  "id_metode": "number",
  "id_jenis": "number",
  "id_bank_go": "number",
  "id_bank_go": "number",
  "id_bank_customer": "number",
  "id_tipe": "number",
  "id_tipe": "number",
  "persen": "number",
  "nominal": "number",
  "kode_rekening": "number",
  "keterangan": "number"
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

### edit list mdr

Request :

- Method : PATCH
- Endpoint : `api/v1/gokasir/mdr/edit/:id`
- Body :

```json
{
  "id_mdr": "number",
  "id_metode": "number",
  "id_jenis": "number",
  "id_bank_go": "number",
  "id_bank_go": "number",
  "id_bank_customer": "number",
  "id_tipe": "number",
  "id_tipe": "number",
  "persen": "number",
  "nominal": "number",
  "kode_rekening": "number",
  "keterangan": "number"
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

### delete list mdr

Request :

- Method : DELETE
- Endpoint : `api/v1/gokasir/mdr/delete/:id`
- Body :

```json
{
  "id_mdr": "number"
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

## Go Expert

### Registrasi

Request :

- Method : GET
- Endpoint : `api/v1/goexpert/registrasi?noregistrasi=${noreg}`

Response :

```json
{
  "data": [
    {
      "pembayaran": [
        {
          "NoRegistrasi": "050213114702",
          "IdPembelian": "1886949",
          "NamaLengkap": "NAJWALINA AZZAHRA",
          "TahunAjaran": "2023/2024",
          "NamaGedung": "PW 34",
          "TanggalDaftar": "2023-10-03",
          "SekolahKelas": "13 ALUMNI IPA",
          "NamaKelas": "13-ALUMNI-R-N-ONLINE",
          "IdBundling": "807135",
          "NamaBundling": "TWT Gap Year Saintek GO Kreasi SNBT 23/24",
          "StatusBayar": "LUNAS",
          "HargaPT": "0",
          "HargaJual": "2000000",
          "TotalHarga": "2000000",
          "Diskon": [
            {
              "id": 2336532,
              "st": "Aktif",
              "jml": 1000000
            }
          ],
          "Pembayaran": [
            {
              "id": 8763815,
              "byr": 0,
              "jml": 0
            },
            {
              "id": 8763816,
              "byr": 1000000,
              "jml": 1000000
            },
            {
              "id": 8763817,
              "byr": 0,
              "jml": 0
            }
          ],
          "JatuhTempo": null,
          "HP": "082252344223",
          "Email": "najwanet04@gmail.com",
          "HPOrtu": "0811587750",
          "EmailOrtu": "ghozali.mh@gmail.com",
          "NoPerjanjian": null,
          "TotalDiskon": 1000000,
          "TotalPembayaran": 1000000,
          "HarusBayar": 1000000,
          "JumlahBayar": 1000000,
          "Sisa": 0
        }
      ],
      "gokreasi": [
        {
          "NoRegistrasi": "050213114702",
          "Email": "najwanet04@gmail.com",
          "NamaLengkap": "NAJWALINA AZZAHRA",
          "IdSekolahKelas": "28",
          "NamaSekolahKelas": "13 ALUMNI IPA",
          "Siapa": "SISWA",
          "Status": "aktif",
          "NomorHP": "082252344223",
          "IsDevice": "1",
          "TerakhirLogin": "2023-10-03 12:32:43"
        },
        {
          "NoRegistrasi": "050213114702",
          "Email": "najwanet04@gmail.com",
          "NamaLengkap": "NAJWALINA AZZAHRA",
          "IdSekolahKelas": "28",
          "NamaSekolahKelas": "13 ALUMNI IPA",
          "Siapa": "ORTU",
          "Status": "aktif",
          "NomorHP": "0811587750",
          "IsDevice": "1",
          "TerakhirLogin": "2023-10-03 15:08:50"
        }
      ]
    }
  ]
}
```


## Bimker

### DAFTAR BIMKER

#### get kewilayahan by kota

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
      "IdKewilayahan": "3",
      "NamaKewilayahan": "Cabang"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get komar

Request :

- Method : POST
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
      "IdKomar": "727",
      "NamaKomar": "L.U Adisucipto 134, Mt. Haryono 6, Moewardi 17"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### Daftar Bimker

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/daftarbimker/getdata?sortby=${Penanda|NamaKomar|Deskripsi|NamaSekolah|SekolahKelas|PerkiaraanJumSis|JumSis|TanggalAwal|TanggalAkhir|Status}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "id_kota": "string",
  "id_kewilayahan": "string",
  "id_komar": "string",
  "status": "string",
  "tahunajaran": "string"
}
```

Response :

```json
{
  "data": [
    {
      "IdKerjasama": "707",
      "IdPenanda": "6",
      "Penanda": "SURAKARTA",
      "IdKomar": "2136",
      "NamaKomar": "MT. Haryono 6",
      "TahunAjaran": "2023/2024",
      "NamaChannel": "Dra. Nurul Qomariah, M.Pd.",
      "Telp": "081802599935",
      "IsDenganSekolah": "1",
      "IdSekolah": "219349",
      "NamaSekolah": "MTSN 1 SURAKARTA",
      "JenjangPendidikan": "MTs",
      "IdDistrict": "199",
      "District": "KOTA SURAKARTA",
      "IdProvinsi": "15",
      "Provinsi": "PROVINSI JAWA TENGAH",
      "IdSekolahKelas": "7",
      "SekolahKelas": "7 SMP UMUM",
      "NilaiKerjasama": "52500000",
      "TahapanPembayaran": "[{\"tahap\": 1, \"jumlah\": 30000000, \"tanggal\": \"2023-09-19\"}, {\"tahap\": 2, \"jumlah\": 22500000, \"tanggal\": \"2024-01-24\"}]",
      "BiayaOperasional": "3000000",
      "PerkiaraanJumSis": "30",
      "Jumsis": "30",
      "BiayaPerSiswa": "1750000",
      "TglJatuhTempo1": "2023-09-19",
      "Deskripsi": "BIMKER MTsN 1 SURAKARTA KELAS 7",
      "TanggalAwal": "2023-09-19",
      "TanggalAkhir": "2024-05-28",
      "JumlahPertemuan": "56",
      "JumlahPertemuanOffline": "56",
      "JumlahPertemuanOnline": "0",
      "JumlahTOBK": "3",
      "JumlahTOBC": "0",
      "Pengali": "1.00",
      "PengaliReal": "1.00",
      "IdBundling": "1222677",
      "NamaBundling": "TWT 7 SMP Bimker MTsN 1 Surakarta KMerdeka 23/24",
      "HargaPT": "0",
      "HargaTotal": "1750000",
      "FileMOU": "ff274912f1d12d2f9df0c673d7f030c8_230925073158.pdf",
      "Status": "Setuju",
      "Updater": "1302501109",
      "LastUpdate": "2023-09-26 10:37:08"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get pembayaran bimker

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/daftarbimker/getpembayaranbimker?sortby=${TglJthTempo|JmlBayar}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "id_kerjasama": "number"
}
```

Response :

```json
{
  "data": [
    {
      "TglJthTempo": "2023-09-26",
      "JmlBayar": "30000000",
      "TglKadaluarsa": "-"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get daftar siswa bimker

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/daftarbimker/getdaftarsiswabimbker?sortby=${NamaSiswa|NamaKelas|JmlBayar}&sort=${asc|desc}&page=${page}&limit=${limit}`
- Body :

```json
{
  "id_kerjasama": "number"
}
```

Response :

```json
{
  "data": [
    {
      "NamaSiswa": "080525022801 - MUHAMMAD ABDULLAH ZAIN ZAIN",
      "NamaKelas": "10-UMUM-R-B-32",
      "JmlBayar": "2000000",
      "BuktiPembayaran": ""
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

#### get file MOU

Request :

- Method : POST
- Endpoint : `api/v1/gokasir/daftarbimker/getfilemou/:id`
- Body :

```json
{
  "id_kerjasama": "number"
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
