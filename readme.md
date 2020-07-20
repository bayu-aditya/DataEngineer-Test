# Data Engineer Test

1. **(SQL)** Buatlah query untuk menampilkan data berikut :
    - Nama customer
    - Income
    - Age
    - Jumlah transaksi
    - Total harga belanja
    - Rata-rata total harga belanja
  
   (Tampilkan data hanya dari tanggal 2 Juni 2020 - 2 Juli 2020)

2. **(SQL)** Buatlah query untuk menampilkan data berikut :
    - Jumlah transaksi
    - Nama customer
    - Rata-rata total belanja per hari
    
    (Tampilkan data hanya dari tanggal 2 Juni 2020 - 2 Juli 2020)


3. **(API)** Berdasarkan database tersebut, buatlah sebuah REST API untuk:

    - Melihat jumlah kuantitas barang yang terjual `n` hari terakhir (asumsi hari ini tanggal 2 Juli 2020, dan `n` adalah integer). Dengan format sebagai berikut:
      - Request:
        >/api/tester/transaction-quantity/last?days=n

      - Response (JSON):
        ```
        {
          data: {
            quantity: int
            }
        }
        ```
        dengan `int` adalah integer.

    - Melihat barang-barang yang terjual berdasarkan ID transaksi (integer), dengan format:
      - Request:
        >/api/tester/transaction?id=n

        dengan `n` merupakan integer.

      - Response (JSON):
        ```
        {
          data: {
            receipt_no: str
            order_no: str
            total_qty: int
            subtotal: int
            tax: int
            total: int
            cash: int
            paid_amount: int
            pay_change: int

            customer: {
              id: int
              name: str
              gender: str
              income: int
              age: int
            }

            detail: [
              {
                id: int
                name: str
                price: int
                qty: int
              }
            ]
          } 
        }
        ```
        dengan `int` dan `str` berturut-turut adalah integer dan string.

4. **(Bash)** Buatlah sebuah bash file untuk membackup data tersebut secara otomatis dengan struktur folder berikut ini:
    ```
    ├── backup.sh
    └── backup_database
        └── 2020
            ├── July
            |   ├── 2020-07-30.sql
            |   └── 2020-07-31.sql
            └── August
                └── 2020-08-01.sql
    ```

    untuk dapat memodifikasi tanggal hari ini, kondisikan bash script sedemikian rupa sehingga dapat dijalankan dengan menggunakan perintah:

    >./backup.sh --today 31-07-2020