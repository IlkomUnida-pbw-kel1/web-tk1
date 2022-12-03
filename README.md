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
        "nama"   : "jafar JS"
        "alamat" : "Bogor"
        "hobi"   : "Hikimg"
    },
    {
    "id" : 1234,
        "nama"   : "jafar JS"
        "alamat" : "Bogor"
        "hobi"   : "Hiking"
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
        "nama"   : "Jafar JS"
        "alamat" : "Bogor"
        "hobi"   : "Hiking"
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

<td> <b>Respon Success</b> </td>
<td>

``` json
{
    "code" : 201,
    "message" : "Data mahasiswa berhasil diinput",
    "data" : {
        "nim" : 2001,
        "nama" : "Jafar JSi",
        "alamat" : "Bogor",
        "hoby" : "Hiking"
    } 
}    
```
<tr>
<td> <b>Respon Conflict</b> </td>
<td>

``` json
{
    "code" : 409,
    "message" : "Nama Mahasiswa telah digunakan",
    "data" : {
        "value" : "Jafar JS",
        "property" : "nama",
        "location" : "body"
    } 
}    
```

</td>
</tr>
</table>
</details>
