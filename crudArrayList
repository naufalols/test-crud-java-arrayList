import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class crudArrayList {

    static Scanner input;
    public static List<String> barang = new ArrayList<String>() {
        {
            add("Panci");
            add("Payung");
            add("Kulkas");
            add("Kursi");
            add("Teralis");
            add("Pintu");
            add("Sepatu");
        }
    };

    public static void main(String[] args) {
        // Script ini based on https://www.petanikode.com/java-file-crud/
        input = new Scanner(System.in);
        // run the program (main loop)
        while (true) {
            menu();
        }
    }

    static void clearScreen() {
        try {
            final String os = System.getProperty("os.name");
            if (os.contains("Windows")) {
                // clear screen untuk windows
                new ProcessBuilder("cmd", "/c", "cls")
                        .inheritIO()
                        .start()
                        .waitFor();
            } else {
                // clear screen untuk Linux, Unix, Mac
                Runtime.getRuntime().exec("clear");
                System.out.print("\033[H\033[2J");
                System.out.flush();
            }
        } catch (final Exception e) {
            System.out.println("Error karena: " + e.getMessage());
        }
    }

    public static void menu() {
        System.out.println("=== LIST MENU ===");
        System.out.println("[1] Lihat Barang");
        System.out.println("[2] Tambah Barang");
        System.out.println("[3] Hapus Barang");
        System.out.println("[4] Cari Barang");
        System.out.println("[0] Keluar");
        System.out.println("---------------------");
        System.out.print("Pilih menu> ");

        String selectedMenu = input.nextLine();

        if (selectedMenu.equals("1")) {
            showBarang();
        } else if (selectedMenu.equals("2")) {
            addBarang();
        } else if (selectedMenu.equals("3")) {
            deleteBarang();
        } else if (selectedMenu.equals("4")) {
            findBarang();
        } else if (selectedMenu.equals("0")) {
            System.exit(0);
        } else {
            clearScreen();
            System.out.println("Anda salah pilih menu!");
            backToMenu();
        }
    }

    static void backToMenu() {
        System.out.println("");
        System.out.print("Tekan [Enter] untuk kembali..");
        input.nextLine();
        clearScreen();
    }

    static void showBarang() {
        clearScreen();

        if (barang.size() <= 0) {
            System.out.println("Data Barang Kosong!");
            backToMenu();

        } else {
            System.out.println("DATA BARANG:");
            int index = 0;
            for (String data : barang) {
                System.out.println(String.format("[%d] %s", index, data));
                index++;
            }
            backToMenu();
        }
    }

    static void addBarang() {
        clearScreen();

        System.out.println("MENAMBAH BARANG");
        System.out.print("Masukkan nama barang : ");

        String namaBarang = input.nextLine();

        try {
            barang.add(namaBarang);
            System.out.print("Berhasil menambahkan barang");
        } catch (Exception e) {
            System.out.println("Terjadi kesalahan karena: " + e.getMessage());
        }

        backToMenu();
    }

    static void readBarang() {

    }

    static void findBarang() {
        clearScreen();

        System.out.println("MENCARI BARANG");
        System.out.print("Cari : ");

        String namaBarang = input.nextLine();
        System.out.println("BARANG YANG DITEMUKAN");
        for (String barang : barang) {
            if (barang.contains(namaBarang)) {
                // String find[] = namaBarang;
                System.out.println(barang);
            }
        }

        backToMenu();

    }

    static void deleteBarang() {
        clearScreen();

        System.out.println("MENGHAPUS BARANG");
        System.out.print("Masukkan nama barang : ");

        String namaBarang = input.nextLine();

        try {
            barang.remove(namaBarang);
            System.out.print("Berhasil menghapus barang");
        } catch (Exception e) {
            System.out.println("Terjadi kesalahan karena: " + e.getMessage());
        }

        backToMenu();
    }
}
