import java.util.Scanner;
import java.util.Map;
import java.util.HashMap;

public class HargaSepatu {
    public static void main(String[] args) {
        // Membuat Map untuk menyimpan data harga sepatu
        Map<String, Map<String, Integer>> hargaSepatu = new HashMap<>();
        hargaSepatu.put("Converse", Map.of("Slip On", 800000, "High Top", 1200000));
        hargaSepatu.put("Sketcher", Map.of("Woman", 1000000, "Man", 1800000));
        hargaSepatu.put("Nike", Map.of("Kids", 750000, "Adult", 1500000));

        // Meminta input dari pengguna
        Scanner scanner = new Scanner(System.in);
        System.out.print("Masukkan merek sepatu: ");
        String merek = scanner.nextLine();
        System.out.print("Masukkan kategori sepatu: ");
        String kategori = scanner.nextLine();

        // Mencari harga sepatu
        Integer harga = hargaSepatu.getOrDefault(merek, Map.of()).get(kategori);

        if (harga != null) {
            System.out.println("Harga sepatu: Rp " + harga);
        } else {
            System.out.println("Sepatu tidak ditemukan");
        }
    }
}
