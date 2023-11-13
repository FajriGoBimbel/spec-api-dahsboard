# API Spec

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
  "c_idbank": "string",
  "c_namabank": "string"
}
```

### get data virtual account

Request

- Method : POST
- Header : null
- Endpoint : `/api/v1/uploadva/getdata?&sortby=${c_NomorVA|c_Peruntukan|c_TanggalUpload|c_Uploader}&sort=${asc|desc}&page=${page}&limit=${limit}`
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
      "c_IdVA": "string",
      "c_IdBank": "number",
      "c_NamaBank": "string",
      "c_NomorVA": "number",
      "c_Peruntukan": "string",
      "c_TanggalUpload": "string",
      "c_Uploader": "string",
      "c_IsTerpakai": "number"
    }
  ],
  "meta": {
    "code": "number",
    "message": "string",
    "status": "string"
  }
}
```

## delete data virtual account

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
 - Endpoint : `/api/v1/uploadva/templateexcel`

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

###