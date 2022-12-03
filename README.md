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

### Read Mahasiswa All
<table>
<tr>
 <td><b> URL </b></td>
<td> {{baseURL}}/api/v1/mahasiswa </td>
</tr>
<tr>
     <td><b> Example </b></td>
    <td> {{baseURL}}/api/v1/mahasiswa?id=1234 </td>
</tr>
<tr>
    <td><b> Method</b> </td>
    <td> GET </td>
</tr>
<tr>
    <td> <b> Header</b>  </td>
<td> Authorization : Bearer Token  </td>
</tr>
<tr>
<td> <b> Query </b>  </td>
<td> id=1234 </td>

<tr>
<td> <b> Respon Success </b>  </td>
<td>

``` Json
{
    "code" : 200,
    "message" : "Sukses",
    "data" : [
    {
        "id"     : 1234,
        "nama"   : "jafar"
        "alamat" : "bogor"
        "hobi"   : "hiking"
    },
    {
    "id" : 1234,
        "nama"   : "jafar"
        "alamat" : "bogor"
        "hobi"   : "hiking"
    }
    ]
}
```
</td>
</tr>
<td> <b> Respon  Conflict </b>  </td>
<td>

``` Json
{
    "code" : 409,
    "message" : "Nama Mahasiswa Telah Digunakan",
    "data" : {
        "nama"   : "jafar"
        "alamat" : "bogor"
        "hobi"   : "hiking"
    }
}
```

</td>
</tr>
<tr>
<td> <b> Respon  Not Found </b>  </td>
<td>

``` Json
{
    "code" : 404,
    "message" : "ID Mahasiswa Tidak Ditemukan",
    "data" : {
        "value"   : 1234,
        "property" : "id"
        "location"   : "query"
    }
}
```
</td>
</tr>
</table>
