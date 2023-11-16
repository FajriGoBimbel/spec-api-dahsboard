# API Spec

# Module Go Icon

## master
## Tingkat Cakupan Kerja

### get list tingkat Cakupan Kerja

Request :

- Method : GET
- Endpoint : `/api/v1/goicons/tingkatcakupankerja`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
                "c_IdKewilayahan": "number",
                "c_NamaKewilayahan": "String",
                "c_Status": "String"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
### create tingkat Cakupan Kerja

Request :

- Method : POST
- Endpoint : `/api/v1/goicons/tingkatcakupankerja`,
- Header : null
- Body :
```json
         {
                "c_NamaKewilayahan": "String",
                "c_Status": "String"
         },
    
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
### Edit tingkat Cakupan Kerja

Request :

- Method : PUT
- Endpoint : `/api/v1/goicons/tingkatcakupankerja`,
- Header : null
- Body :
```json
         {
                "c_IdKewilayahan": "number",
                "c_NamaKewilayahan": "String",
                "c_Status": "String"
         },
    
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
### Delete tingkat Cakupan Kerja

Request :

- Method : Delete
- Endpoint : `/api/v1/goicons/tingkatcakupankerja/{idkewilayahan}`,
- Header : null
- Body :
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


### get list cakupan kerja

Request :

- Method : GET
- Endpoint : `/api/v1/goicons/cakupankerja`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
            {
                "id": "number",
                "name": "string",
                "namakomar": "string",
                "idtree": "number",
                "idjenistree":"number",
                "jenistree": "number",
                "c_Upline": "number",
                "parentid": "number",
                "c_IdPenanda":"number",
                "kota": "string",
                "isgedung": "string",
                "alamat":"string"
            },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
  
### get list Penanda

Request :

- Method : GET
- Endpoint : `/api/v1/goicons/penanda`,
- Header : null
- Body :

Response :

```json
    {
        "data": [
             {
            "c_IdPenanda": "number",
            "c_Penanda":  "string",
            "id": "number",
            "name":  "string"
        },
        ],
        "meta": {
            "code": "number",
            "message": "string",
            "status": "string"
        }
    }
```
  
