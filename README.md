**Nama** : Wirya Dharma Kurnia <br />
**NPM** : 2306152115 <br />
**Kelas** : Adpro <br />

## Reflection

### 1.2: Understanding how it works
![image1](images/image1.png)

Saya menambahkan baris `println!("Wirya's Computer: hey hey")` setelah `spawner.spawn()` pada file `main.rs`. Namun, jika kita lihat dari screenshot outputnya, baris `Wirya's Computer: hey hey` muncul lebih dahulu daripada `Wirya's Computer: howdy!` dan `Wirya's Computer: done`. Hal ini terjadi karena baris `Wirya's Computer: hey hey` berada di luar async block, sehingga akan langsung dieksekusi tanpa dimasukkan ke queue eksekusi. Sementara itu, baris kode yang berada pada async block baru akan dieksekusi ketika berada di line `executor.run()` di paling bawah kode, setelah `println!("Wirya's Computer: hey hey)`. Karena itulah baris `Wirya's Computer: hey hey` akan keluar terlebih dahulu, baru block async akan dijalankan yang kemudian menghasilkan output `Wirya's Computer: howdy!` dan `Wirya's Computer: done`.
