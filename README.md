# **Pembuatan dokumentasi sederhana untuk rancangan request API service yang memuat permintaan CRUD atau method POST,GET,PUT dan DELETE**

Berikutnya adalah, perlu diketahui juga http method apa yang digunakan untuk sebuah proses CRUD melalui API. Berikut adalah http method yang biasanya digunakan untuk kebutuhan CRUD dasar.

**1. POST — CREATE**  
     Method POST biasa digunakan untuk melakukan request untuk membuat resource baru. Method POST ini biasanya akan diarahkan kepada method create pada Controller.
   
**2. GET — SHOW / INDEX**   
     Method GET biasa digunakan untuk melakukan request untuk mengambil atau menampilkan resource. Resource yang ditampilkan atau diambil bisa hanya satu atau semuanya      yang ada (indexing). Method GET ini akan diarahkan kepada Controller pada bagian method show untuk menampilan sebuah resource atau method index untuk menampilkan      banyak resource. 

**3. PUT — UPDATE (all)** 
     Method PUT biasa digunakan untuk melakukan request untuk melakukan perubahan pada semua elemen dari suatu resource, kecuali bagian Id atau primary key dari   
     resource tersebut. Method GET ini akan diarahkan kepada method update pada Controller.
 
**4. DELETE — DESTROY**  
     Method DELETE biasa digunakan untuk melakukan request untuk menghapus resource. Method DELETE ini biasanya akan diarahkan kepada method destroy pada Controller.
 

## Agenda Mahasiswa Ilmu Komputer

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

## Data Dosen Ilmu Komputer
<details>
<summary> Klik untuk Ekspan </summary>

### Create Dosen
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/dosen </td>
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
    "nama" : "Uus Firdaus",
    "alamat" : "Gadog",
    "mapel" : "Basisdata, Struktur Data",
    "kelas" : "Pagi, Sore"
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
    "message" : "Data Dosen Berhasil diinput",
    "data" : {
        "nid" : 0010201,
        "nama" : "Uus Firdaus",
        "alamat" : "Gadog",
        "mapel" : "Basisdata, Struktur Data",
        "kelas" : "Pagi, Sore"
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
    "message" : "Nama Dosen Telah digunakan",
    "data" : {
        "value" : "Uus Firdaus",
        "property" : "nama",
        "location" : "body"
    } 
}    
```
    
</td>
</tr>
</table>

### Read Dosen By nid
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/dosen </td>
</tr>
<tr>
    <td> <b>Example</b> </td>
    <td> {{baseURL}}/api/v1/dosen?nid=0010201 </td>
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
<td> nid=0010201 </td>
</tr>
<tr>
<td> <b>Respon Success</b> </td>
<td>

``` json
{
    "code" : 200,
    "message" : "Sukses",
    "data" : {
        "nid" : 0010201,
        "nama" : "Uus Firdaus",
        "alamat" : "Gadog",
        "mapel" : "Basisdata, Struktur Data",
        "kelas" : "Pagi, Sore"
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
    "message" : "NID Dosen tidak ditemukan",
    "data" : {
        "value" : 0010201,
        "property" : "nid",
        "location" : "query"
    } 
}    
```

</td>
</tr>
</table>


### Read Dosen All
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/dosen </td>
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
    "data" : 
        {
            "nid" : 0010201,
            "nama" : "Uus Firdaus",
            "alamat" : "Gadog",
            "mapel" : "Basisdata, Struktur Data",
            "kelas" : "Pagi, Sore"
        },
        {
            "nid" : 0010202,
            "nama" : "Hilmy Aliy Andra Putra",
            "alamat" : "Ciapus",
            "mapel" : "Matematika, Aljabar Linear",
            "kelas" : "Pagi, Sore"
        },
        {
            "nid" : 0010203,
            "nama" : "Mash'um Abdul Jabbar",
            "alamat" : "Megamendung",
            "mapel" : "OOP, PBW",
            "kelas" : "Pagi, Sore"
        }
    
}    
```

</td>
</tr>
</table>

### Update Dosen
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/dosen </td>
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
    "nid" : 0010203,
    "nama" : "Mash'um Abdul Jabbar, M.T.I",
    "alamat" : "Megamendung",
    "mapel" : "OOP, PBW",
    "kelas" : "Pagi, Sore"
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
    "message" : "Data Dosen Berhasil diubah",
    "data" : {
        "nid" : 0010203,
        "nama" : "Mash'um Abdul Jabbar, M.T.I",
        "alamat" : "Megamendung",
        "mapel" : "OOP, PBW",
        "kelas" : "Pagi, Sore"
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
    "message" : "Nama Dosen Telah digunakan",
    "data" : {
        "value" : "Mash'um Abdul Jabbar, M.T.I",
        "property" : "nama",
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
    "message" : "NID Dosen tidak ditemukan",
    "data" : {
        "value" : 0010203,
        "property" : "nid",
        "location" : "body"
    } 
}    
```

</td>
</tr>
</table>

### Delete Dosen
<table>
<tr>
    <td> <b>URL</b> </td>
    <td> {{baseURL}}/api/v1/dosen </td>
</tr>
<tr>
    <td> <b>Example</b> </td>
    <td> {{baseURL}}/api/v1/dosen?nid=0010201 </td>
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
<td> nid=0010201 </td>
</tr>
<tr>
<td> <b>Respon Success</b> </td>
<td>

``` json
{
    "code" : 200,
    "message" : "Sukses dihapus",
    "data" : {
        "nid" : 0010201,
        "nama" : "Uus Firdaus",
        "alamat" : "Gadog",
        "mapel" : "Basisdata, Struktur Data",
        "kelas" : "Pagi, Sore"
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
    "message" : "NID Dosen tidak ditemukan",
    "data" : {
        "value" : 0010201,
        "property" : "nid",
        "location" : "query"
    } 
}    
```

</td>
</tr>
</table>
</details>
