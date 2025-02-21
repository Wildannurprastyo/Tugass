1. Mengimpor Scanner
import java.util.Scanner;
Fungsi: Mengimpor kelas Scanner dari pustaka java.util, yang digunakan untuk membaca input dari pengguna.
2. Deklarasi Kelas
public class Kpl1_UAS;
3. Metode main (Program Utama)
public static void main(String[] args) {
public → Bisa diakses dari luar kelas.
static → Dapat dijalankan tanpa membuat objek dari kelas.
void → Tidak mengembalikan nilai (tidak ada return).
main → Metode utama yang dieksekusi pertama kali.
String[] args → Parameter array untuk menerima input dari command line (tidak digunakan di sini).
4. Membuat Objek Scanner
Scanner input = new Scanner(System.in);
Scanner → Kelas untuk membaca input dari keyboard.
input → Nama variabel yang digunakan untuk Scanner.
new Scanner(System.in) → Membuat objek Scanner yang membaca input dari keyboard (System.in).
5. Deklarasi Array dan Variabel
String[] namaMahasiswa = new String[100];
String[] nimMahasiswa = new String[100];
String[] jenisPrestasi = new String[100];
String[] tingkatPrestasi = new String[100];
int[] tahunPrestasi = new int[100];
int prestasiCount = 0;
int pilihan;
String[] namaMahasiswa = new String[100]; → Array untuk menyimpan nama mahasiswa.
String[] nimMahasiswa = new String[100]; → Array untuk menyimpan NIM mahasiswa.
String[] jenisPrestasi = new String[100]; → Array untuk menyimpan jenis prestasi.
String[] tingkatPrestasi = new String[100]; → Array untuk menyimpan tingkat prestasi.
int[] tahunPrestasi = new int[100]; → Array untuk menyimpan tahun prestasi (dalam angka).
int prestasiCount = 0; → Variabel untuk menghitung jumlah data prestasi.
int pilihan; → Variabel untuk menyimpan pilihan menu dari pengguna.
6. Menampilkan Menu dengan do-while
do {
    System.out.println("=== PENCATATAN PRESTASI MAHASISWA ===");
    System.out.println("1. Tambah Prestasi Mahasiswa");
    System.out.println("2. Tampilkan Daftar Prestasi");
    System.out.println("3. Analisis Prestasi Berdasarkan Jenis");
    System.out.println("4. Keluar");
    System.out.print("Pilih menu: ");
    pilihan = input.nextInt();
    input.nextLine();
do { ... } while (pilihan != 4); → Perulangan agar menu terus muncul sampai pengguna memilih keluar (4).
System.out.println(...) → Menampilkan menu pilihan di layar.
System.out.print("Pilih menu: "); → Meminta pengguna memasukkan angka menu.
pilihan = input.nextInt(); → Membaca input angka dari pengguna.
input.nextLine(); → Menghindari bug input agar tidak loncat.
7. Pilihan 1: Tambah Data Prestasi
case 1:
    if (prestasiCount >= 100) { 
        System.out.println("Data sudah penuh!");
        break;
    }
    System.out.print("Masukkan Nama Mahasiswa: ");
    namaMahasiswa[prestasiCount] = input.nextLine();
    System.out.print("Masukkan NIM: ");
    nimMahasiswa[prestasiCount] = input.nextLine();
    System.out.print("Masukkan Jenis Prestasi: ");
    jenisPrestasi[prestasiCount] = input.nextLine();
    System.out.print("Masukkan Tingkat Prestasi: ");
    tingkatPrestasi[prestasiCount] = input.nextLine();
    System.out.print("Masukkan Tahun Prestasi: ");
    tahunPrestasi[prestasiCount] = input.nextInt();
    input.nextLine();
    prestasiCount++;
    System.out.println("Data berhasil ditambahkan!");
    break;
Jika data sudah mencapai 100, tampilkan pesan "Data sudah penuh!".
Meminta input pengguna untuk Nama, NIM, Jenis Prestasi, Tingkat Prestasi, dan Tahun Prestasi.
Menyimpan data ke dalam array masing-masing.
Meningkatkan prestasiCount agar jumlah data bertambah.
Menampilkan pesan "Data berhasil ditambahkan!".
8. Pilihan 2: Tampilkan Daftar Prestasi
case 2:
    if (prestasiCount == 0) {
        System.out.println("Belum ada data prestasi.");
    } else {
        System.out.println("=== DAFTAR PRESTASI ===");
        for (int i = 0; i < prestasiCount; i++) {
            System.out.println((i + 1) + ". " + namaMahasiswa[i] + " - " +
                               nimMahasiswa[i] + " - " + jenisPrestasi[i] +
                               " - " + tingkatPrestasi[i] + " - " + tahunPrestasi[i]);
        }
    }
    break;

Jika belum ada data, tampilkan "Belum ada data prestasi.".

Jika ada data, tampilkan semua data dengan perulangan for.
10. Pilihan 3: Analisis Prestasi Berdasarkan Jenis
case 3:
    if (prestasiCount == 0) {
        System.out.println("Belum ada data prestasi.");
    } else {
        System.out.print("Masukkan jenis prestasi yang ingin dianalisis: ");
        String cariJenis = input.nextLine();
        int jumlah = 0;
        for (int i = 0; i < prestasiCount; i++) {
            if (jenisPrestasi[i].equalsIgnoreCase(cariJenis)) {
                jumlah++;
            }
        }
        System.out.println("Jumlah prestasi dengan jenis '" + cariJenis + "': " + jumlah);
    }
    break;
Meminta pengguna memasukkan jenis prestasi yang ingin dihitung.
Menggunakan perulangan for untuk menghitung jumlah prestasi dengan jenis yang dimasukkan.
Menampilkan hasil jumlah prestasi berdasarkan jenis tersebut.
11. Pilihan 4: Keluar dari Program
case 4:
    System.out.println("Terima kasih!");
    break;
default:
    System.out.println("Pilihan tidak valid!");
}
Jika pengguna memilih 4, program keluar dengan pesan "Terima kasih!".
Jika input tidak sesuai dengan menu, tampilkan "Pilihan tidak valid!".
12. Menutup Scanner
input.close();
Menutup Scanner untuk menghindari kebocoran memori.
