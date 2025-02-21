1. Deklarasi Variabel:
String[] namaMahasiswa = new String[100];
String[] nimMahasiswa = new String[100];
String[] jenisPrestasi = new String[100];
String[] tingkatPrestasi = new String[100];
int[] tahunPrestasi = new int[100];
int prestasiCount = 0;
Variabel-variabel di atas digunakan untuk menyimpan informasi mengenai mahasiswa dan prestasi mereka:
namaMahasiswa[] : //Menyimpan nama mahasiswa.
nimMahasiswa[] : //Menyimpan NIM mahasiswa.
jenisPrestasi[] : //Menyimpan jenis prestasi yang diperoleh.
tingkatPrestasi[] : //Menyimpan tingkat prestasi (Lokal, Nasional, Internasional).
tahunPrestasi[] : //Menyimpan tahun prestasi diraih.
prestasiCount : //Menyimpan jumlah prestasi yang sudah dimasukkan, digunakan untuk melacak jumlah data yang dimasukkan.
2. Menu Utama:
do {
    System.out.println("=== PENCATATAN PRESTASI MAHASISWA ===");
    System.out.println("1. Tambah Prestasi Mahasiswa");
    System.out.println("2. Tampilkan Daftar Prestasi");
    System.out.println("3. Analisis Prestasi Berdasarkan Jenis");
    System.out.println("4. Keluar");
    System.out.print("Pilih menu: ");
    pilihan = input.nextInt();
    input.nextLine();
//Program menampilkan menu dengan pilihan sebagai berikut:
Tambah Prestasi Mahasiswa: Menambahkan prestasi mahasiswa baru.
Tampilkan Daftar Prestasi: Menampilkan daftar prestasi yang sudah dimasukkan.
Analisis Prestasi Berdasarkan Jenis: Menampilkan prestasi berdasarkan jenis prestasi yang dimasukkan.
Keluar: Keluar dari program.
3. Case 1 - Tambah Prestasi Mahasiswa:
if (prestasiCount >= 100) { 
    System.out.println("Jumlah prestasi telah mencapai batas maksimal."); 
    break; 
} 

System.out.print("Nama Mahasiswa: "); 
namaMahasiswa[prestasiCount] = input.nextLine(); 
System.out.print("NIM: "); 
nimMahasiswa[prestasiCount] = input.nextLine(); 
System.out.print("Jenis Prestasi: "); 
jenisPrestasi[prestasiCount] = input.nextLine(); 
while (true) { 
    System.out.print("Tingkat Prestasi (Lokal, Nasional, Internasional): "); 
    tingkatPrestasi[prestasiCount] = input.nextLine(); 
    if (tingkatPrestasi[prestasiCount].equalsIgnoreCase("Lokal") || 
    tingkatPrestasi[prestasiCount].equalsIgnoreCase("Nasional") || 
    tingkatPrestasi[prestasiCount].equalsIgnoreCase("Internasional")) {
        break; 
    } else { 
        System.out.println("Input tidak valid. Harap masukkan salah satu dari: Lokal, Nasional, Internasional."); 
    } 
}
while (true) { 
    System.out.print("Tahun Prestasi (2010 hingga tahun saat ini): "); 
    int tahun = input.nextInt(); 
    input.nextLine(); 
    if (tahun >= 2010 && tahun <= 2024) { 
        tahunPrestasi[prestasiCount] = tahun; 
        break; 
    } else { 
        System.out.println("Input tidak valid. Harap masukkan tahun antara 2010 hingga tahun saat ini."); 
    } 
}

prestasiCount++; 
System.out.println("Prestasi berhasil ditambahkan!");
//Pada pilihan pertama, program meminta input data prestasi mahasiswa: nama, NIM, jenis prestasi, tingkat prestasi (Lokal, Nasional, Internasional), dan tahun prestasi.
Ada pengecekan untuk memastikan tingkat prestasi hanya dapat diisi dengan "Lokal", "Nasional", atau "Internasional".
Selain itu, tahun prestasi harus berada dalam rentang tahun 2010 hingga 2024.
Setelah data berhasil dimasukkan, prestasiCount akan bertambah dan data prestasi akan disimpan di array.
4. Case 2 - Tampilkan Daftar Prestasi:
if (prestasiCount > 0) {
    System.out.println("=== DAFTAR SEMUA PRESTASI ==="); 
    for (int i = 0; i < prestasiCount; i++) { 
        System.out.println("Nama: " + namaMahasiswa[i] + "| NIM: " + nimMahasiswa[i] + "| Jenis: " + jenisPrestasi[i] + "| Tingkat: " + tingkatPrestasi[i] + "| Tahun: " + tahunPrestasi[i]); 
    }
} else {
    System.out.println("belum ada data prestasi");
}                  
//Pada pilihan kedua, program akan menampilkan semua prestasi yang telah dimasukkan.
Jika belum ada prestasi yang dimasukkan, program akan menampilkan pesan "belum ada data prestasi."
5. Case 3 - Analisis Prestasi Berdasarkan Jenis:
System.out.print("Masukkan jenis prestasi yang ingin dianalisis: "); 
String jenis = input.nextLine(); 
System.out.println("=== ANALSIS PRESTASI ==="); 
for (int i = 0; i < prestasiCount; i++) { 
    if (jenisPrestasi[i].equalsIgnoreCase(jenis)) { 
        System.out.println("Nama: " + namaMahasiswa[i] + "| NIM: " + nimMahasiswa[i] + "| Tingkat: " + tingkatPrestasi[i] + "| Tahun: " + tahunPrestasi[i]); 
    } 
}
//Pada pilihan ketiga, program meminta input jenis prestasi yang ingin dianalisis (misalnya "Lokal", "Nasional", atau "Internasional").
Kemudian, program menampilkan semua prestasi yang memiliki jenis yang sama dengan input yang dimasukkan oleh pengguna.
6. Case 4 - Keluar:
System.out.println("Terima kasih!");
//Pada pilihan keempat, program menampilkan pesan "Terima kasih!" dan kemudian keluar dari loop, menghentikan eksekusi program.
7. Default - Pilihan Tidak Valid:
System.out.println("Pilihan tidak valid. Silakan coba lagi.");
//Jika pengguna memasukkan pilihan yang tidak ada di menu, program akan menampilkan pesan kesalahan dan meminta input ulang.
