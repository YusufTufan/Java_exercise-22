# Kelime Listeleme
Bu program, bir cümledeki kelimeleri listeleyerek bir ArrayList'e ekler.

## Nasıl Çalışır?
Program, verilen bir cümleyi döngüyle tarar ve her bir kelimeyi bir ArrayList'e ekler. Cümledeki boşluk karakterlerini kullanarak kelimeleri ayırır.

## Kullanım
1. Java derleyicisi kullanarak `Kelime_Listeleme.java` dosyasını derleyin:
   ```sh
   javac Kelime_Listeleme.java
   ```

2. Programı çalıştırın:
   ```sh
   java Kelime_Listeleme
   ```

## Örnek
```java
import java.util.ArrayList;

public class Kelime_Listeleme {
    public static void main(String[] args) {
        String cumle = "Bu bir test cümlesidir.";
        System.out.println("Listelenecek cümle: " + cumle);
        ArrayList<String> kelimeler = kelimelisteleme(cumle);

        System.out.println("Kelimeler:");
        for (String kelime : kelimeler) {
            System.out.println(kelime);
        }
    }

    public static ArrayList<String> kelimelisteleme(String cumle) {
        ArrayList<String> kelimeler = new ArrayList<>();
        int startindex = 0;

        for (int i = 0; i < cumle.length(); i++) {
            if (cumle.charAt(i) == ' ') {
                String kelime = cumle.substring(startindex, i);
                kelimeler.add(kelime);
                startindex = i + 1;
            }
        }
        String sonKelime = cumle.substring(startindex);
        kelimeler.add(sonKelime);
        return kelimeler;
    }
}
```

Bu README.md dosyası, programın ne yaptığını, nasıl kullanılacağını ve içerdiği örnek kod parçacığını detaylı bir şekilde açıklıyor.
