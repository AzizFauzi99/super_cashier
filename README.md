# Tentang
Self-service cashier sederhana dengan menggunakan bahasa pemrograman Python.

## Latar Belakang
- Ketika berjualan barang akan sangat menyita waktu jika harus mencatat barang pembelian dan menghitung keseluruhan harga yang harus dibayar dari pembeli secara manual, misalnya di selembar kertas.
- Ketika banyak pembeli yang datang sedangkan pelayanan yang tersedia untuk melayani sangat terbatas, maka pembeli harus menunggu terlebih dahulu agar bisa dilayani. Ini tentunya akan membuat kepuasan pembeli menjadi menurun
- Diperlukannya sebuah sistem kasir yang dapat secara cepat dan tepat mencatat dan menghitung barang pembelian dari pembeli secara otomatis dan mandiri.

## Requirements/Objective
- Membuat proses menyelesaikan permasalahan kasir self-service untuk membantu pedagang berjualan.
- Membuat proses untuk `menambahkan barang` belanjaan.
- Membuat proses untuk `menghapus barang` belanjaan.
- Membuat proses untuk `edit nama` barang belanjaan.
- Membuat proses untuk `edit jumlah` barang belanjaan. 
- Membuat proses untuk `edit harga` barang belanjaan.
- Membuat proses untuk `menghitung total harga` barang belanjaan.
- Membuat proses untuk `menghitung diskon` barang belanjaan.
- Membuat proses untuk `mengosongkan barang` belanjaan.
- Mengecek barang belanjaan dengan `menampilkan seluruh barang belanjaan`.

## Flowchart
![1](https://user-images.githubusercontent.com/92005833/218294325-e69cbb25-3a30-46dc-8eb7-39dd528d5692.jpg)

## Penjelasan Fungsi
Semua fungsi berikut terdapat di dalam class bernama `Transaction` pada file `main.py`:

#### Method
- `add_item`. Menambahkan barang dengan format `add_item([item_name, quantity, price_per_item])` ke dalam variable `items` di dalam class. Contoh: `add_item(['Ayam', 12, 15_000])`
- `delete_item`. Menghapus barang berdasarkan nama di dalam `items` jika tersedia dengan format `delete_item(item_name)`. Contoh: `delete_item('Ayam')`
- `update_item_name`. Mengganti nama barang saat ini dengan nama barang yang baru jika barang yang disebutkan tersedia dengan format `update_item_name(old_name, new_name)`. Contoh: `update_item_name('Ayam', 'Ayam Goreng')`
- `update_item_qty`. Mengganti jumlah pesanan barang jika barang yang disebutkan tersedia dengan format `update_item_name(item_name, new_qty)`. Contoh: `update_item_qty('Ayam', 20)`.
- `update_item_price`. Mengganti harga per item barang jika barang yang disebutkan tersedia dengan format `update_item_price(item_name, new_price)`. Contoh `update_item_price('Ayam', 30_000)`
- `calculate_total_price`. Menghitung harga total semua barang.
- `check_order`. Menampilkan semua barang yang telah ditambahkan beserta dengan total harga keseluruhan.
- `reset_transaction`. Mengosongkan semua barang sekaligus yang telah ditambahkan.
- `total_price_print`. Menampilkan seluruh barang beserta total harga tiap barang, discount, dan total setelah diskon.

#### Generic Function
- `__init__`. Menginisiasi variable utama pada sebuah class. Dalam hal ini adalah variable `items` yang dinisiasi.
- `calculate_discount`. Menghitung jika total keseluruhan harga barang memenuhi syarat diskon. Syarat diskon adalah sebagai berikut:
	1. Jika di atas Rp 200.000 diskon sebesar 5%
	2. Jika di atas Rp 300.000 diskon sebesar 8%
	3. Jika di atas Rp 500.000 diskon sebesar 10%

#### Modul
- `validate_add_item`. Validasi sebelum item ditambahkan. Meliputi format penulisan dan harga barang/qty tidak boleh negatif.
- `validate_update_item_name`. Validasi sebelum item diganti namanya. Meliputi format penulisan nama item baru dan nama item lama.
- `validate_update_item_qty`. Validasi sebelum qty item diupdate. Meliputi format penulisan dan qty tidak boleh negatif.
- `validate_update_item_price`. Validasi sebelum harga item diupdate. Meliputi format penulisan dan harga tidak boleh negatif.

## Demonstrasi Code
Membuat Customer1 dengan code `Customer1 = Transaction()` <br>
![1](https://user-images.githubusercontent.com/92005833/218295769-816b89e0-df05-4109-a6db-8e22f64af122.jpg)

### Test 1: add_item()
Customer ingin menambahkan dua item baru menggunakan method `add_item()`. Item yang ditambahkan adalah sebagai berikut:
- Nama Item: Bakso, Qty: 2, Harga: 12000
- Nama Item: Mie Ayam, Qty: 3, Harga: 10000

**Output:** <br>
![2](https://user-images.githubusercontent.com/92005833/218295843-e6f84c7a-44a6-4068-8955-e99f79e306ef.PNG)

### Test 2: delete_item()
Ternyata Customer salah membeli salah satu item dari belanjaan yang sudah ditambahkan, maka Customer menggukan method `delete_item()` untuk menghapus item. Item yang ingin dihapuskan adalah **Bakso**.

**Output:** <br>
![1](https://user-images.githubusercontent.com/92005833/218295935-f1c9d53a-fb9c-429c-acae-b4352e7d3b54.PNG)

### Test 3: reset_transaction()
Ternyata setelah dipikir-pikir, Customer salah memasukkan item yang ingin dibelanjakan! Daripada menghapusnya satu - satu, maka Customer cukup menggunakan method `reset_transaction()` untuk menghapus semua item yang sudah ditambahkan.

**Output:** <br>
![3](https://user-images.githubusercontent.com/92005833/218296087-6f4613cb-718f-444d-bccf-b2e0ab4fad18.PNG)

### Test 4: total_price_print()
Setelah Customer selesai berbelanja, akan menghitung total belanja yang harus dibayarkan menggunakan method `total_price_print()`. Sebelum mengeluarkan output total belanja akan menampilkan item - item yang dibeli.

**Output:** <br>
![1 2](https://user-images.githubusercontent.com/92005833/218296142-5fbac0cb-c7cc-4568-9581-e49b22f579cc.PNG)
![1 3](https://user-images.githubusercontent.com/92005833/218296147-6f3b0d58-a874-44e3-9cb5-81eb064b2941.PNG)

### Test 5: update_item_name()
Mngganti nama **Bakso** yang terlanjur ditambahkan menggunakan metode `update_item_name()` sehingga nama item tersebut menjadi **Soto**

**Output:** <br>
![1](https://user-images.githubusercontent.com/92005833/218296227-54441342-b46e-4446-aea8-516cd90b62b3.PNG)

### Test 6: update_item_qty()
Customer ingin mengganti Quantity dari **Steak** yang sebelumnya 3 buah menjadi 2 buah dengan metode `update_item_qty()`

**Output:** <br>
![1](https://user-images.githubusercontent.com/92005833/218296397-e3f7af30-9083-4c5a-9f7c-0d2e13d0e2d4.PNG)

### Test 7: update_item_price()
Customer ingin mengganti harga per item dari **Steak** yang sebelumnya 100000 menjadi 150000 per item-nya dengan metode `update_item_price()`.

**Output**: <br>
![2](https://user-images.githubusercontent.com/92005833/218296475-f763a046-e45e-488b-b513-89a0c9e3a496.PNG)

### Test 8: Validasi sebelum menambahkan item <br>
![1](https://user-images.githubusercontent.com/92005833/218296547-c3fc8f33-5480-4738-8cb9-b3771aad24e7.PNG)

### Test 9: Validasi sebelum nama item diganti <br>
![1](https://user-images.githubusercontent.com/92005833/218296645-ff0613cd-c5ce-4f48-9915-d9fabf44aaac.PNG)

### Test 10: Validasi sebelum qty item diganti <br>
![2](https://user-images.githubusercontent.com/92005833/218296650-59145aa1-f6f5-4297-a850-fabe21e3b98d.PNG)

### Test 11: Validasi sebelum harga item diganti <br>
![3](https://user-images.githubusercontent.com/92005833/218296656-05629e2d-7847-47d5-a7fc-645ad2041889.PNG)

## Kesimpulan
- Super cashier adalah program sederhana yang membantu penjual untuk menjual produknya secara efektif dan efisien.
- Terdapat fitur menambahkan barang, mengedit barang (nama, quantity, harga per item), menghapus barang, dan menjumlahkan keseluruhan harga barang beserta diskonnya secara cepat dan tepat.
- Keseluruhan fitur tersebut dapat memudahkan dan mempercepat pembeli untuk membeli barangnya secara mandiri.

## Future Work
- Membuat GUI (_Graphical User Interface_)
- Membuat sistem pembayaran yang terintegrasi dengan sistem kasir
