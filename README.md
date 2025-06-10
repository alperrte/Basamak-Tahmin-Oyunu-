import java.util.*;

public class main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Random random = new Random();

        String sayi = Integer.toString(random.nextInt(9000) + 1000); 
        System.out.print("Sayiyi tahmin edin: ");

        while (true) {
            String tahmin = input.nextLine();

            if (tahmin.length() != 4) {
                System.out.println("Lütfen 4 basamaklı bir sayı girin.");
                continue;
            }

            int arti = 0;
            int eksi = 0;

            if (tahmin.equals(sayi)) {
                System.out.println("Doğru tahmin!");
                break;
            }

            for (int i = 0; i < 4; i++) {
                if (tahmin.charAt(i) == sayi.charAt(i)) {
                    arti++;
                } else if (sayi.contains(String.valueOf(tahmin.charAt(i)))) {
                    eksi++;
                }
            }

            if (arti == 0 && eksi == 0) {
                System.out.println("0");
            } else {
                if (arti != 0) System.out.println("+" + arti);
                if (eksi != 0) System.out.println("-" + eksi);
            }
        }
    }
}
