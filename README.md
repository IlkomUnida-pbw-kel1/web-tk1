# Agenda Mahasiswa Ilmu Komputer
##

## Data Mahasiswa Ilmu Komputer
<details>
<summary> Klik untuk Ekspan </summary>

### Create Mahasiswa
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/mahasiswa </td>
</tr>
<tr>
    <td> <b>Method</b> </td>
    <td> POST </td>
</tr>
<tr>
    <td> <b>Header</b> </td>
    <td> Authorization : Bearer Token  </td>
</tr>    
<tr>
<td> <b>Body</b> </td>
<td>

``` json
{
    "nama" : "Rusdi Abdul Gani",
    "alamat" : "Bogor",
    "hoby" : "Musik"
}    
```
</td>
</tr>
<tr>
<td> <b>Respon Success</b> </td>
<td>

``` json
{
    "code" : 201,
    "message" : "Data Mahasiswa berhasil diinput",
    "data" : {
        "nim" : 2001,
        "nama" : "Rusdi Abdul Gani",
        "alamat" : "Bogor",
        "hoby" : "Musik"
    } 
}    
```

</td>
</tr>
<tr>
<td> <b>Respon Conflict</b> </td>
<td>

``` json
{
    "code" : 409,
    "message" : "Nama Mahasiswa telah digunakan",
    "data" : {
        "value" : "Rusdi Abdul Gani",
        "property" : "nama",
        "location" : "body"
    } 
}    
```

</td>
</tr>
</table>

### Read Mahasiswa By nim
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/mahasiswa </td>
</tr>
<tr>
    <td> <b>Example</b> </td>
    <td> {{baseURL}}/api/v1/mahasiswa?nim=2001 </td>
</tr>
<tr>
    <td> <b>Method</b> </td>
    <td> GET </td>
</tr>
<tr>
    <td> <b>Header</b> </td>
    <td> Authorization : Bearer Token  </td>
</tr>
<tr>
<td> <b>Query</b> </td>
<td> nim=2001 </td>
</tr>
<tr>
<td> <b>Respon Success</b> </td>
<td>

``` json
{
    "code" : 200,
    "message" : "Sukses",
    "data" : {
        "nim" : 2001,
        "nama" : "Rusdi Abdul Gani",
        "nim" : "20.1.1",
        "alamat" : "Bogor",
        "hoby" : "Musik"
    } 
}    
```

</td>
</tr>
<tr>
<td> <b>Respon Not Found</b> </td>
<td>

``` json
{
    "code" : 404,
    "message" : "NIM Mahasiswa tidak ditemukan",
    "data" : {
        "value" : 2001,
        "property" : "nim",
        "location" : "query"
    } 
}    
```

</td>
</tr>
</table>

### Read Mahasiswa All
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/mahasiswa </td>
</tr>
<tr>
    <td> <b>Method</b> </td>
    <td> GET </td>
</tr>
<tr>
    <td> <b>Header</b> </td>
    <td> Authorization : Bearer Token  </td>
</tr>
<tr>
<td> <b>Respon Success</b> </td>
<td>

``` json
{
    "code" : 200,
    "message" : "Sukses",
    "data" : [
        {
            "nim" : 2001,
            "nama" : "Rusdi Abdul Gani",
            "alamat" : "Bogor",
            "hoby" : "Musik"
        },
        {
            "nim" : 2002,
            "nama" : "Risa",
            "alamat" : "Bogor",
            "hoby" : "Game"
        },
        {
            "nim" : 2003,
            "nama" : "Jafar Sodik",
            "alamat" : "Tajur",
            "hoby" : "Membaca"
        },
        {
            "nim" : 2004,
            "nama" : "Fajar HKM",
            "alamat" : "Cisarua",
            "hoby" : "Olahraga"
        },
        {
            "nim" : 2005,
            "nama" : "M. Fikri",
            "alamat" : "Gadog",
            "hoby" : "Game"
        }
    ]
}    
```

</td>
</tr>
</table>

### Update Mahasiswa
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/mahasiswa </td>
</tr>
<tr>
    <td> <b>Method</b> </td>
    <td> PUT </td>
</tr>
<tr>
    <td> <b>Header</b> </td>
    <td> Authorization : Bearer Token  </td>
</tr>
<tr>
<td> <b>Body</b> </td>
<td>

``` json
{
    "nim" : 2001,
    "nama" : "Rusdi Abdul Gani",
    "alamat" : "Ciberem",
    "hoby" : "Coding"
}    
```

</td>
</tr>
<tr>
<td> <b>Respon Success</b> </td>
<td>

``` json
{
    "code" : 201,
    "message" : "Data Mahasiswa berhasil diubah",
    "data" : {
        "nim" : 2001,
        "nama" : "Rusdi Abdul Gani",
        "alamat" : "Ciberem",
        "hoby" : "coding"
    } 
}    
```

</td>
</tr>
<tr>
<td> <b>Respon Conflict</b> </td>
<td>

``` json
{
    "code" : 409,
    "message" : "Alamat Mahasiswa telah digunakan",
    "data" : {
        "value" : "Ciberem",
        "property" : "alamat",
        "location" : "body"
    } 
}    
```

</td>
</tr>
<tr>
<td> <b>Respon Not Found</b> </td>
<td>

``` json
{
    "code" : 404,
    "message" : "NIM Mahasiswa tidak ditemukan",
    "data" : {
        "value" : 2001,
        "property" : "nim",
        "location" : "body"
    } 
}    
```

</td>
</tr>
</table>

### Delete Mahasiswa
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/mahasiswa </td>
</tr>
<tr>
    <td> <b>Example</b> </td>
    <td> {{baseURL}}/api/v1/mahasiswa?nim=2001 </td>
</tr>
<tr>
    <td> <b>Method</b> </td>
    <td> DELETE </td>
</tr>
<tr>
    <td> <b>Header</b> </td>
    <td> Authorization : Bearer Token  </td>
</tr>
<tr>
<td> <b>Query</b> </td>
<td> nim=2001 </td>
</tr>
<tr>
<td> <b>Respon Success</b> </td>
<td>

``` json
{
    "code" : 200,
    "message" : "Sukses dihapus",
    "data" : {
        "nim" : 2001,
        "nama" : "Rusdi Abdul Gani",
        "alamat" : "Ciberem",
        "hoby" : "Coding"
    }
}    
```

</td>
</tr>
<tr>
<td> <b>Respon Not Found</b> </td>
<td>

``` json
{
    "code" : 404,
    "message" : "NIM Mahasiswa tidak ditemukan",
    "data" : {
        "value" : 2001,
        "property" : "nim",
        "location" : "query"
    } 
}    
```

</td>
</tr>
</table>
</details>
