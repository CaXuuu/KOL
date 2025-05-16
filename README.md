package KOL;

import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.List;
import java.util.Scanner;


public class Main {

    private static final String FILE_PATH = "C:/Users/macie/IdeaProjects/javakol1/src/KOL/test.txt";

    public static void main(String[] args) {
        System.out.println("Podaj jakis tekst");
Scanner scanner = new Scanner(System.in);
String text = scanner.nextLine();
        System.out.println("Podales: "+text);


       swriteTextToFile(text);

        Path path = Paths.get(FILE_PATH);
        try {
            System.out.println("zawartosc pliku:");
            List<String> strings = Files.readAllLines(path);
            for(String fileText :strings){
                System.out.println(fileText);
            }
        } catch (IOException e) {
            throw new RuntimeException(e);
        }


    }

    private static void writeTextToFile(String text) {
        try {
            FileWriter fileWriter = new FileWriter(FILE_PATH);
            PrintWriter printWriter = new PrintWriter(fileWriter);
            printWriter.println("zawartosc: ");
            printWriter.println(text);
            printWriter.close();
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }
}

nt jeden = 2;
int dwa = 3;
Integer.compare(jeden, dwa);
String str1 = "jakis trestk"
String str2 = "jakis inny tekst"
str.compareTo(str2);

wykorzystanie np.
gdy lista przechowuje String
List#sort((c1, c2) -> c1.compareTo(c2))

//String#split([znak dzielnik]) - dzieli tekst przez podany znak
    //String#split([znak dzielnik], [limit]) - dzieli tekst przez podany znak
    //String#replace([co zamienić], [na co zamienić]) - zamienia podany znak na inny w tekście
    //String#toLowerCase
    //String#toUpperCase
    //String#trim - usuwa spacje z początku i końca tekstu
    // "  dkskstas sadi qwrn yt   " -> "dkskstas sadi qwrn yt"
    //String#length - długość
    //String#toCharArray -
    //String#equals -
    //String#equalsIgnoreCase - "asssa" == "ASSsA" true

    //ogólne#var - zapis do zmiennej
    //ogólne#fori - pętla for liczbowa
    //ogóle#for - pętla po tablicy


    // KONSTRUKTOR – tworzenie obiektu
public class Osoba {
    String imie;
    public Osoba(String imie) {
        this.imie = imie;
    }
}
Osoba o = new Osoba("Jan");

// KLASA ABSTRAKCYJNA – nie można stworzyć obiektu, tylko dziedziczyć
public abstract class Zwierze {
    public abstract void dajGlos();
}
public class Pies extends Zwierze {
    public void dajGlos() {
        System.out.println("Hau!");
    }
}
Zwierze z = new Pies();
z.dajGlos();

// INTERFEJS – kontrakt
interface Latajacy {
    void lec();
}
class Ptak implements Latajacy {
    public void lec() {
        System.out.println("Lecę!");
    }
}

// DZIEDZICZENIE – rozszerzanie klasy bazowej
public class Osoba {
    String imie;
    public Osoba(String imie) {
        this.imie = imie;
    }
}
public class Student extends Osoba {
    int indeks;
    public Student(String imie, int indeks) {
        super(imie);
        this.indeks = indeks;
    }
}

// toString – reprezentacja tekstowa obiektu
@Override
public String toString() {
    return "Student: " + imie + ", indeks: " + indeks;
}
System.out.println(o); // automatycznie używa toString()

// equals i hashCode – porównywanie obiektów
@Override
public boolean equals(Object obj) {
    if (this == obj) return true;
    if (obj == null || getClass() != obj.getClass()) return false;
    Osoba osoba = (Osoba) obj;
    return imie.equals(osoba.imie);
}
@Override
public int hashCode() {
    return imie.hashCode();
}

// Comparable – sortowanie obiektów
public class Osoba implements Comparable<Osoba> {
    String imie;
    public int compareTo(Osoba o) {
        return this.imie.compareTo(o.imie);
    }
}
Collections.sort(lista);

// Comparator – sortowanie po innych kryteriach
Comparator<Osoba> cmp = new Comparator<Osoba>() {
    public int compare(Osoba o1, Osoba o2) {
        return o1.wiek - o2.wiek;
    }
};
Collections.sort(lista, cmp);

// SCANNER – wczytywanie danych z pliku
import java.io.File;
import java.util.Scanner;
try {
    File plik = new File("dane.txt");
    Scanner sc = new Scanner(plik);
    while (sc.hasNextLine()) {
        String linia = sc.nextLine();
        System.out.println(linia);
    }
    sc.close();
} catch (Exception e) {
    e.printStackTrace();
}

// ZAPIS DO PLIKU
import java.io.FileWriter;
try {
    FileWriter fw = new FileWriter("wynik.txt");
    fw.write("Wynik zapisu");
    fw.close();
} catch (Exception e) {
    e.printStackTrace();
}

// ArrayList – dynamiczna tablica
import java.util.ArrayList;
ArrayList<Osoba> lista = new ArrayList<>();
lista.add(new Osoba("Jan"));
Osoba o = lista.get(0);

// foreach – iteracja po kolekcji
for (Osoba o : lista) {
    System.out.println(o);
}

// METODA STATYCZNA
public class Narzedzia {
    public static int dodaj(int a, int b) {
        return a + b;
    }
}
int wynik = Narzedzia.dodaj(2, 3);

// GETTERY I SETTERY
private String imie;
public String getImie() {
    return imie;
}
public void setImie(String imie) {
    this.imie = imie;
}

// MODYFIKATORY DOSTĘPU
// public – dostęp wszędzie
// private – tylko w klasie
// protected – klasa i dziedziczące
// brak (package-private) – w tym samym pakiecie

// IMPORT I PAKIETY
package mojpakiet;
import java.util.*;
import java.io.*;

// OBSŁUGA WYJĄTKÓW
try {
    int x = 5 / 0;
} catch (ArithmeticException e) {
    System.out.println("Dzielenie przez zero!");
}

// POLIMORFIZM – wspólny typ bazowy
Zwierze z = new Pies();
z.dajGlos(); // Hau!

// KLASA WEWNĘTRZNA
class Zewnetrzna {
    class Wewnetrzna {
        void pokaz() {
            System.out.println("Jestem wewnętrzna");
        }
    }
}

// ENUM – typ wyliczeniowy
enum Dzien {
    PON, WTO, SRO
}
Dzien d = Dzien.PON;

// VARARGS – wiele argumentów
public void wypisz(String... args) {
    for (String s : args) System.out.println(s);
}

// THIS i SUPER
this.imie = imie;      // odwołanie do pola klasy
super.metoda();        // wywołanie metody klasy bazowej

// FINAL – niezmienne
final int x = 5;       // stała
final class A {}       // nie można dziedziczyć
final void metoda() {} // nie można przesłaniać

// KOPIOWANIE OBIEKTU – klonowanie
class Osoba implements Cloneable {
    public Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}

// INTERFEJSY W JDK
// Comparable – naturalne sortowanie
// Comparator – alternatywne sortowanie
// Serializable – zapis do pliku
// Iterable – foreach
// Runnable – wątki

// PRZYKŁAD PĘTLI
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
while (true) {
    break;
}
do {
    System.out.println("raz");
} while (false);

// TABLICE
int[] tab = new int[5];
String[] imiona = {"Jan", "Anna"};
System.out.println(imiona[0]);

// STRINGI
String a = "Ala";
String b = "Ala";
a.equals(b); // true
a == b;      // true, bo to ten sam obiekt (dla literałów)

// KONWERSJE
int x = Integer.parseInt("123");
String y = String.valueOf(123);

// DATE I TIME (Java 8+)
import java.time.LocalDate;
LocalDate dzis = LocalDate.now();
System.out.println(dzis);

// WYŚWIETLANIE
System.out.print("Bez nowej linii");
System.out.println("Z nową linią");
System.out.printf("Wartość: %d", 5);

// SCANNER z klawiatury
Scanner sc = new Scanner(System.in);
System.out.print("Podaj imię: ");
String imie = sc.nextLine();
System.out.println("Cześć, " + imie);


// 🔹 Importy przydatne globalnie
import java.util.*;
import java.io.*;
import java.time.*;

// 🔹 Klasa główna z main (zawsze potrzebna)
public class Main {
    public static void main(String[] args) {
        // 🔸 Scanner z klawiatury
        Scanner sc = new Scanner(System.in);
        System.out.print("Podaj imię: ");
        String imie = sc.nextLine();
        System.out.println("Cześć, " + imie);

        // 🔸 ArrayList – lista dynamiczna
        ArrayList<String> imiona = new ArrayList<>();
        imiona.add(imie);
        imiona.add("Kasia");
        imiona.add("Tomek");

        // 🔸 Pętla for-each
        for (String s : imiona) {
            System.out.println("Witaj: " + s);
        }

        // 🔸 Map – para klucz-wartość
        Map<String, Integer> wiek = new HashMap<>();
        wiek.put("Jan", 22);
        wiek.put("Anna", 25);
        System.out.println("Wiek Anny: " + wiek.get("Anna"));

        // 🔸 Sortowanie listy
        Collections.sort(imiona);
        System.out.println("Posortowane: " + imiona);

        // 🔸 Data i czas
        LocalDate dzis = LocalDate.now();
        System.out.println("Dziś jest: " + dzis);

        // 🔸 Wyjątek – try/catch
        try {
            int dzielenie = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Błąd: " + e.getMessage());
        }

        // 🔸 Metoda statyczna
        int suma = Narzedzia.dodaj(2, 5);
        System.out.println("Suma: " + suma);

        // 🔸 Obiekt + toString
        Student s = new Student("Ola", 123);
        System.out.println(s);

        // 🔸 Odczyt z pliku
        try {
            Scanner plik = new Scanner(new File("dane.txt"));
            while (plik.hasNextLine()) {
                System.out.println("Plik: " + plik.nextLine());
            }
            plik.close();
        } catch (Exception e) {
            System.out.println("Błąd pliku: " + e.getMessage());
        }

        // 🔸 Zapis do pliku
        try {
            FileWriter fw = new FileWriter("wynik.txt");
            fw.write("Zapisano imię: " + imie);
            fw.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

// 🔹 Klasa pomocnicza – metoda statyczna
class Narzedzia {
    public static int dodaj(int a, int b) {
        return a + b;
    }
}

// 🔹 Klasa z konstruktorem, toString i equals
class Student {
    private String imie;
    private int indeks;

    public Student(String imie, int indeks) {
        this.imie = imie;
        this.indeks = indeks;
    }

    @Override
    public String toString() {
        return "Student: " + imie + ", indeks: " + indeks;
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (!(obj instanceof Student)) return false;
        Student s = (Student) obj;
        return indeks == s.indeks && imie.equals(s.imie);
    }

    @Override
    public int hashCode() {
        return Objects.hash(imie, indeks);
    }
}


// Clock.java
import java.time.LocalTime;
import java.time.format.DateTimeFormatter;

public abstract class Clock {
    protected LocalTime time;
    protected City city;

    public Clock(City city) {
        this.city = city;
        setCurrentTime();
    }

    public void setCurrentTime() {
        this.time = LocalTime.now().plusHours(city.getTimezone());
        updateHands();
    }

    public void setTime(int hour, int minute, int second) {
        if (hour < 0 || hour > 23) throw new IllegalArgumentException("Godzina poza zakresem 0-23");
        if (minute < 0 || minute > 59) throw new IllegalArgumentException("Minuta poza zakresem 0-59");
        if (second < 0 || second > 59) throw new IllegalArgumentException("Sekunda poza zakresem 0-59");
        this.time = LocalTime.of(hour, minute, second);
        updateHands();
    }

    public void setCity(City newCity) {
        int diff = newCity.getTimezone() - city.getTimezone();
        this.time = this.time.plusHours(diff);
        this.city = newCity;
        updateHands();
    }

    public String toString() {
        return time.format(DateTimeFormatter.ofPattern("HH:mm:ss"));
    }

    protected void updateHands() {}
}

// DigitalClock.java
public class DigitalClock extends Clock {
    public enum ClockFormat { H12, H24 }
    private ClockFormat format;

    public DigitalClock(City city, ClockFormat format) {
        super(city);
        this.format = format;
    }

    @Override
    public String toString() {
        if (format == ClockFormat.H24) {
            return super.toString();
        } else {
            DateTimeFormatter formatter = DateTimeFormatter.ofPattern("h:mm:ss a");
            return time.format(formatter);
        }
    }
}

// City.java
import java.io.*;
import java.time.LocalTime;
import java.util.*;

public class City {
    private String name;
    private int timezone;
    private double latitude;
    private double longitude;

    public City(String name, int timezone, double latitude, double longitude) {
        this.name = name;
        this.timezone = timezone;
        this.latitude = latitude;
        this.longitude = longitude;
    }

    public static City parseLine(String line) {
        String[] parts = line.split(",");
        String name = parts[0];
        int tz = Integer.parseInt(parts[1]);
        double lat = parseCoordinate(parts[2]);
        double lon = parseCoordinate(parts[3]);
        return new City(name, tz, lat, lon);
    }

    public static Map<String, City> parseFile(String path) throws IOException {
        Map<String, City> map = new HashMap<>();
        try (BufferedReader reader = new BufferedReader(new FileReader(path))) {
            reader.readLine(); // skip header
            String line;
            while ((line = reader.readLine()) != null) {
                City city = parseLine(line);
                map.put(city.getName(), city);
            }
        }
        return map;
    }

    private static double parseCoordinate(String s) {
        s = s.trim();
        double value = Double.parseDouble(s.substring(0, s.length() - 2));
        char direction = s.charAt(s.length() - 1);
        return (direction == 'S' || direction == 'W') ? -value : value;
    }

    public LocalTime localMeanTime(LocalTime zoneTime) {
        double hoursOffset = longitude / 15.0;
        int seconds = (int) (hoursOffset * 3600);
        return zoneTime.plusSeconds(seconds);
    }

    public static Comparator<City> worstTimezoneFit() {
        return (c1, c2) -> {
            LocalTime z1 = LocalTime.NOON;
            LocalTime z2 = LocalTime.NOON;
            long diff1 = Math.abs(java.time.Duration.between(z1, c1.localMeanTime(z1)).getSeconds());
            long diff2 = Math.abs(java.time.Duration.between(z2, c2.localMeanTime(z2)).getSeconds());
            return Long.compare(diff2, diff1);
        };
    }

    public static void generateAnalogClocksSvg(List<City> cities, AnalogClock clock) throws IOException {
        File dir = new File(clock.toString());
        dir.mkdir();
        for (City c : cities) {
            clock.setCity(c);
            clock.toSvg(clock.toString() + "/" + c.getName() + ".svg");
        }
    }

    public String getName() { return name; }
    public int getTimezone() { return timezone; }
    public double getLongitude() { return longitude; }
}

// ClockHand.java
import java.time.LocalTime;

public abstract class ClockHand {
    protected double angle;
    public abstract void setTime(LocalTime t);
    public abstract String toSvg();
}

// SecondHand.java
public class SecondHand extends ClockHand {
    @Override
    public void setTime(LocalTime t) {
        angle = t.getSecond() * 6;
    }

    @Override
    public String toSvg() {
        return String.format("<line x1=\"100\" y1=\"100\" x2=\"100\" y2=\"20\" stroke=\"red\" stroke-width=\"1\" transform=\"rotate(%.2f 100 100)\"/>", angle);
    }
}

// MinuteHand.java
public class MinuteHand extends ClockHand {
    @Override
    public void setTime(LocalTime t) {
        angle = t.getMinute() * 6 + t.getSecond() * 0.1;
    }

    @Override
    public String toSvg() {
        return String.format("<line x1=\"100\" y1=\"100\" x2=\"100\" y2=\"30\" stroke=\"black\" stroke-width=\"2\" transform=\"rotate(%.2f 100 100)\"/>", angle);
    }
}

// HourHand.java
public class HourHand extends ClockHand {
    @Override
    public void setTime(LocalTime t) {
        angle = t.getHour() % 12 * 30 + t.getMinute() * 0.5 + t.getSecond() * (0.5 / 60);
    }

    @Override
    public String toSvg() {
        return String.format("<line x1=\"100\" y1=\"100\" x2=\"100\" y2=\"50\" stroke=\"black\" stroke-width=\"3\" transform=\"rotate(%.2f 100 100)\"/>", angle);
    }
}

// AnalogClock.java
import java.io.FileWriter;
import java.io.IOException;
import java.util.List;

public class AnalogClock extends Clock {
    private final List<ClockHand> hands = List.of(new HourHand(), new MinuteHand(), new SecondHand());

    public AnalogClock(City city) {
        super(city);
    }

    @Override
    protected void updateHands() {
        for (ClockHand hand : hands) {
            hand.setTime(time);
        }
    }

    public void toSvg(String path) throws IOException {
        StringBuilder sb = new StringBuilder();
        sb.append("<svg width=\"200\" height=\"200\" xmlns=\"http://www.w3.org/2000/svg\">\n");
        sb.append("<circle cx=\"100\" cy=\"100\" r=\"95\" stroke=\"black\" stroke-width=\"2\" fill=\"white\" />\n");
        for (ClockHand hand : hands) {
            sb.append(hand.toSvg()).append("\n");
        }
        sb.append("</svg>");
        try (FileWriter writer = new FileWriter(path)) {
            writer.write(sb.toString());
        }
    }
}

// Main.java
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        Map<String, City> cityMap = City.parseFile("strefy.csv");
        City warszawa = cityMap.get("Warszawa");
        DigitalClock clock24 = new DigitalClock(warszawa, DigitalClock.ClockFormat.H24);
        DigitalClock clock12 = new DigitalClock(warszawa, DigitalClock.ClockFormat.H12);
        System.out.println(clock24);
        System.out.println(clock12);

        AnalogClock analog = new AnalogClock(warszawa);
        analog.toSvg("Warszawa.svg");

        List<City> cities = new ArrayList<>(cityMap.values());
        cities.sort(City.worstTimezoneFit());
        for (City c : cities) {
            System.out.println(c.getName());
        }

        City.generateAnalogClocksSvg(cities, analog);
    }
}
------------
---------------
------------
--------------
--------------
// Sciagawka z Programowania Obiektowego (Java) - Kolokwium

// 1. Klasa abstrakcyjna Clock
public abstract class Clock {
    protected int hour, minute, second;

    public void setCurrentTime() {
        LocalTime now = LocalTime.now();
        this.hour = now.getHour();
        this.minute = now.getMinute();
        this.second = now.getSecond();
    }

    public void setTime(int hour, int minute, int second) {
        if (hour < 0 || hour > 23) throw new IllegalArgumentException("Invalid hour: " + hour);
        if (minute < 0 || minute > 59) throw new IllegalArgumentException("Invalid minute: " + minute);
        if (second < 0 || second > 59) throw new IllegalArgumentException("Invalid second: " + second);
        this.hour = hour;
        this.minute = minute;
        this.second = second;
    }

    @Override
    public String toString() {
        return String.format("%02d:%02d:%02d", hour, minute, second);
    }
}

// 2. Enum - tryb zegara
public enum TimeFormat {
    H24, H12
}

// 3. Dziedziczenie: DigitalClock z formatem 12/24h
public class DigitalClock extends Clock {
    private TimeFormat format;

    public DigitalClock(TimeFormat format) {
        this.format = format;
    }

    @Override
    public String toString() {
        if (format == TimeFormat.H24) {
            return super.toString();
        } else {
            int hour12 = hour % 12;
            hour12 = (hour12 == 0) ? 12 : hour12;
            String period = (hour < 12) ? "AM" : "PM";
            return String.format("%d:%02d:%02d %s", hour12, minute, second, period);
        }
    }
}

// 4. Wczytywanie CSV i przetwarzanie danych: City
public class City {
    private String name;
    private int timezoneOffset;
    private double latitude, longitude;

    public City(String name, int timezoneOffset, double latitude, double longitude) {
        this.name = name;
        this.timezoneOffset = timezoneOffset;
        this.latitude = latitude;
        this.longitude = longitude;
    }

    public static City parseLine(String line) {
        String[] parts = line.split(",");
        String name = parts[0];
        int offset = Integer.parseInt(parts[1]);
        double lat = parseCoordinate(parts[2]);
        double lon = parseCoordinate(parts[3]);
        return new City(name, offset, lat, lon);
    }

    private static double parseCoordinate(String coord) {
        coord = coord.trim();
        double value = Double.parseDouble(coord.replaceAll("[^0-9.-]", ""));
        return coord.endsWith("S") || coord.endsWith("W") ? -value : value;
    }

    public static Map<String, City> parseFile(String path) throws IOException {
        Map<String, City> map = new HashMap<>();
        List<String> lines = Files.readAllLines(Paths.get(path));
        for (int i = 1; i < lines.size(); i++) {
            City c = parseLine(lines.get(i));
            map.put(c.name, c);
        }
        return map;
    }

    public LocalTime localMeanTime(LocalTime zoneTime) {
        double hourShift = (longitude / 180.0) * 12;
        return zoneTime.plusSeconds((long)(hourShift * 3600));
    }

    public static Comparator<City> worstTimezoneFit() {
        return Comparator.comparingDouble(c -> {
            double geoHours = (c.longitude / 180.0) * 12;
            return Math.abs(c.timezoneOffset - geoHours);
        }).reversed();
    }

    @Override
    public String toString() {
        return name;
    }
}

// 5. Klasa abstrakcyjna ClockHand
public abstract class ClockHand {
    protected double angle;
    public abstract void setTime(LocalTime time);
    public abstract String toSvg();
}

// 6. SecondHand - wskazówka sekundowa
public class SecondHand extends ClockHand {
    public void setTime(LocalTime time) {
        this.angle = time.getSecond() * 6;
    }

    public String toSvg() {
        return svgLine(angle, 90, "red", 1);
    }
}

// 7. HourHand & MinuteHand
public class HourHand extends ClockHand {
    public void setTime(LocalTime time) {
        this.angle = (time.getHour() % 12 + time.getMinute() / 60.0 + time.getSecond() / 3600.0) * 30;
    }
    public String toSvg() {
        return svgLine(angle, 50, "black", 4);
    }
}

public class MinuteHand extends ClockHand {
    public void setTime(LocalTime time) {
        this.angle = (time.getMinute() + time.getSecond() / 60.0) * 6;
    }
    public String toSvg() {
        return svgLine(angle, 70, "black", 2);
    }
}

// 8. Pomocnicza metoda do rysowania linii SVG
private static String svgLine(double angle, int length, String color, int width) {
    double rad = Math.toRadians(angle - 90);
    int x2 = (int)(100 + length * Math.cos(rad));
    int y2 = (int)(100 + length * Math.sin(rad));
    return String.format("<line x1=\"100\" y1=\"100\" x2=\"%d\" y2=\"%d\" stroke=\"%s\" stroke-width=\"%d\" />", x2, y2, color, width);
}

// 9. AnalogClock z generowaniem SVG
public class AnalogClock extends Clock {
    private final List<ClockHand> hands = List.of(
        new HourHand(), new MinuteHand(), new SecondHand()
    );

    public void updateHands() {
        LocalTime time = LocalTime.of(hour, minute, second);
        for (ClockHand h : hands) h.setTime(time);
    }

    public void toSvg(String path) throws IOException {
        updateHands();
        StringBuilder svg = new StringBuilder();
        svg.append("<svg width=\"200\" height=\"200\" xmlns=\"http://www.w3.org/2000/svg\">\n");
        svg.append("<circle cx=\"100\" cy=\"100\" r=\"90\" stroke=\"black\" stroke-width=\"3\" fill=\"white\" />\n");
        for (ClockHand h : hands) svg.append(h.toSvg()).append("\n");
        svg.append("</svg>");
        Files.writeString(Paths.get(path), svg.toString());
    }
}

// 10. City.generateAnalogClocksSvg - tworzenie plików SVG
public static void generateAnalogClocksSvg(List<City> cities, AnalogClock clock) throws IOException {
    String dir = clock.toString().replace(":", "_");
    Files.createDirectories(Paths.get(dir));
    for (City city : cities) {
        clock.setTime(clock.hour, clock.minute, clock.second); // resetuje na główny czas
        LocalTime time = LocalTime.of(clock.hour, clock.minute, clock.second);
        LocalTime cityTime = city.localMeanTime(time);
        clock.setTime(cityTime.getHour(), cityTime.getMinute(), cityTime.getSecond());
        clock.toSvg(dir + "/" + city.toString() + ".svg");
    }
}

// Przydatne klasy i metody Java:
// - LocalTime.now(), LocalTime.of(h, m, s)
// - Files.readAllLines(Paths.get(path)) - odczyt pliku
// - Files.writeString(Paths.get(path), content) - zapis pliku
// - List<String> lines = Files.readAllLines(...)
// - Map<String, City> map = new HashMap<>()
// - Comparator.comparingDouble(...)
// - String.format(...) do formatowania napisów
-----------
-------------
------------
--------------
-------------
------------
---------------
-----------
// ========================== KLASY I OBIEKTY ==========================
// Klasa – szablon obiektu
public class Osoba {
    // pola (atrybuty)
    private String imie;
    private int wiek;

    // konstruktor – tworzy obiekt i ustawia pola
    public Osoba(String imie, int wiek) {
        this.imie = imie;
        this.wiek = wiek;
    }

    // metody (zachowanie)
    public void przedstawSie() {
        System.out.println("Cześć, jestem " + imie + ", mam " + wiek + " lat.");
    }
}

// Tworzenie obiektu
Osoba o = new Osoba("Jan", 30);
o.przedstawSie();  // wywołanie metody

// ========================== ENKAPSULACJA I KONSTRUKTORY ==========================
// Enkapsulacja – ukrywanie danych za pomocą private + dostęp przez gettery/settery
public class Konto {
    private double saldo;

    public Konto(double saldoPoczatkowe) {
        if (saldoPoczatkowe < 0) saldoPoczatkowe = 0;
        this.saldo = saldoPoczatkowe;
    }

    public double getSaldo() {
        return saldo;
    }

    public void wplata(double kwota) {
        if (kwota > 0) saldo += kwota;
    }

    public void wyplata(double kwota) {
        if (kwota > 0 && saldo >= kwota) saldo -= kwota;
    }
}

// ========================== DZIEDZICZENIE ==========================
// Dziedziczenie – tworzenie nowej klasy na podstawie istniejącej (extends)
public class Zwierze {
    public void dajGlos() {
        System.out.println("Jakieś zwierzę");
    }
}

public class Pies extends Zwierze {
    @Override
    public void dajGlos() {
        System.out.println("Hau Hau!");
    }
}

// Użycie polimorfizmu
Zwierze z = new Pies();
z.dajGlos();  // "Hau Hau!"

// ========================== ABSTRAKCJA ==========================
// Klasa abstrakcyjna – nie można tworzyć obiektów, tylko dziedziczyć i implementować metody abstrakcyjne
public abstract class Figura {
    public abstract double pole();
}

public class Kolo extends Figura {
    private double promien;

    public Kolo(double promien) {
        this.promien = promien;
    }

    @Override
    public double pole() {
        return Math.PI * promien * promien;
    }
}

// Interfejsy – definiują zestaw metod do implementacji
interface Latajacy {
    void lec();
}

class Ptak implements Latajacy {
    public void lec() {
        System.out.println("Lecę wysoko!");
    }
}

// ========================== KONTENERY (KOLEKCJE) ==========================
// Lista dynamiczna
import java.util.ArrayList;
ArrayList<String> lista = new ArrayList<>();
lista.add("Jan");
lista.add("Anna");
System.out.println(lista.get(0));  // "Jan"

// Mapy – przechowują pary klucz-wartość
import java.util.HashMap;
HashMap<String, Integer> mapa = new HashMap<>();
mapa.put("Jan", 25);
mapa.put("Anna", 30);
System.out.println(mapa.get("Anna"));  // 30

// Iteracja po kolekcjach
for (String imie : lista) {
    System.out.println(imie);
}

// Sortowanie kolekcji
import java.util.Collections;
Collections.sort(lista);  // sortuje alfabetycznie

// ========================== PLIKI I WYJĄTKI ==========================
// Odczyt z pliku
import java.io.File;
import java.util.Scanner;

try {
    Scanner plik = new Scanner(new File("dane.txt"));
    while (plik.hasNextLine()) {
        String linia = plik.nextLine();
        System.out.println(linia);
    }
    plik.close();
} catch (Exception e) {
    System.out.println("Błąd: " + e.getMessage());
}

// Zapis do pliku
import java.io.FileWriter;

try {
    FileWriter fw = new FileWriter("wynik.txt");
    fw.write("Hello World");
    fw.close();
} catch (Exception e) {
    System.out.println("Błąd zapisu: " + e.getMessage());
}

// Obsługa wyjątków – try, catch, finally
try {
    int wynik = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Nie można dzielić przez zero!");
} finally {
    System.out.println("Blok finally wykonany zawsze");
}

// Rzucanie wyjątków – throw i throws
public void sprawdz(int wiek) throws IllegalArgumentException {
    if (wiek < 0) throw new IllegalArgumentException("Wiek nie może być ujemny");
}

// ========================== PROGRAMOWANIE FUNKCYJNE ==========================
// Lambda – uproszczona funkcja anonimowa
import java.util.function.Function;
Function<Integer, Integer> kwadrat = x -> x * x;
System.out.println(kwadrat.apply(5));  // 25

// Predykat – funkcja zwracająca boolean
import java.util.function.Predicate;
Predicate<String> jestPusty = s -> s.isEmpty();
System.out.println(jestPusty.test(""));  // true

// Stream API – operacje na kolekcjach (Java 8+)
import java.util.List;
import java.util.stream.Collectors;

List<String> imiona = Arrays.asList("Jan", "Anna", "Piotr");
List<String> dlugieImiona = imiona.stream()
    .filter(s -> s.length() > 3)
    .collect(Collectors.toList());
System.out.println(dlugieImiona);  // [Anna, Piotr]

// Metoda referencyjna (method reference)
imiona.forEach(System.out::println);

// ========================== DODATKOWE PRZYDATNE KONSTRUKCJE ==========================
// toString – reprezentacja tekstowa obiektu
@Override
public String toString() {
    return "Osoba{" + "imie='" + imie + '\'' + ", wiek=" + wiek + '}';
}

// equals i hashCode – porównywanie obiektów
@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (!(o instanceof Osoba)) return false;
    Osoba osoba = (Osoba) o;
    return wiek == osoba.wiek && imie.equals(osoba.imie);
}
@Override
public int hashCode() {
    return Objects.hash(imie, wiek);
}

// Konstruktor kopiujący
public Osoba(Osoba inna) {
    this.imie = inna.imie;
    this.wiek = inna.wiek;
}

// Metoda statyczna
public static int dodaj(int a, int b) {
    return a + b;
}

// Klasa anonimowa (np. Comparator)
Collections.sort(lista, new Comparator<String>() {
    @Override
    public int compare(String o1, String o2) {
        return o1.length() - o2.length();
    }
});

// Final – stałe i niezmienne
final int MAX = 100;

// Praca z tablicami
int[] tab = {1, 2, 3, 4};
for (int x : tab) {
    System.out.println(x);
}
-----------
------------
-------------
--------------
--------------
------------
// ========================== PRAKTYCZNE DODATKI I WZORCE ==========================

// 1. Wzorzec Singleton – klasa, która ma tylko jedną instancję
public class Singleton {
    private static Singleton instance;

    private Singleton() {}  // prywatny konstruktor

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}

// 2. Builder – wygodny sposób budowania obiektów z wieloma opcjonalnymi polami
public class OsobaBuilder {
    private String imie;
    private int wiek;

    public OsobaBuilder setImie(String imie) {
        this.imie = imie;
        return this;
    }

    public OsobaBuilder setWiek(int wiek) {
        this.wiek = wiek;
        return this;
    }

    public Osoba build() {
        return new Osoba(imie, wiek);
    }
}
// Użycie:
// Osoba o = new OsobaBuilder().setImie("Jan").setWiek(30).build();

// 3. Optional – bezpieczna praca z wartościami, które mogą być null
import java.util.Optional;

Optional<String> imie = Optional.ofNullable(null);
System.out.println(imie.orElse("Brak imienia"));  // wypisze "Brak imienia"

// 4. Formatowanie tekstu – printf, String.format
System.out.printf("Wiek: %d, Imię: %s%n", 30, "Jan");
String tekst = String.format("Cena: %.2f zł", 15.6789);
System.out.println(tekst);

// 5. Stream API – filtrowanie, mapowanie, redukcja kolekcji
List<Integer> liczby = Arrays.asList(1, 2, 3, 4, 5);
int sumaParzystych = liczby.stream()
    .filter(x -> x % 2 == 0)
    .mapToInt(x -> x)
    .sum();
System.out.println("Suma parzystych: " + sumaParzystych);

// 6. Metody referencyjne (method references)
List<String> lista = Arrays.asList("ala", "kot", "pies");
lista.stream()
    .map(String::toUpperCase)
    .forEach(System.out::println);

// 7. Klasy generyczne – typy parametryzowane
public class Para<T, U> {
    private T pierwszy;
    private U drugi;

    public Para(T pierwszy, U drugi) {
        this.pierwszy = pierwszy;
        this.drugi = drugi;
    }

    public T getPierwszy() { return pierwszy; }
    public U getDrugi() { return drugi; }
}
Para<String, Integer> p = new Para<>("Wiek", 30);
System.out.println(p.getPierwszy() + ": " + p.getDrugi());

// 8. Auto-boxing / unboxing
Integer x = 10;      // automatycznie zamienione na Integer
int y = x;           // automatycznie zamienione na int

// 9. Praca z datą i czasem – API java.time (Java 8+)
LocalDate data = LocalDate.of(2023, 5, 16);
LocalDate dzis = LocalDate.now();
Period wiek = Period.between(data, dzis);
System.out.println("Liczba lat: " + wiek.getYears());

// 10. Konkretne wyjątki do łapania – np. IOException, NumberFormatException
try {
    int n = Integer.parseInt("abc");
} catch (NumberFormatException e) {
    System.out.println("To nie jest liczba!");
}

// 11. Szybkie czytanie całej linii z pliku lub inputu
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
String linia = br.readLine();  // wymaga obsługi IOException

// 12. Konstruktor kopiujący i klonowanie (Cloneable)
public Osoba(Osoba o) {
    this.imie = o.imie;
    this.wiek = o.wiek;
}

@Override
public Osoba clone() throws CloneNotSupportedException {
    return (Osoba) super.clone();
}

// 13. Synchronized – synchronizacja wątków
public synchronized void bezpiecznaMetoda() {
    // kod bezpieczny dla wielowątkowości
}

// 14. Enum z metodami
public enum Dzien {
    PONIEDZIALEK(1), WTOREK(2);

    private int nr;

    Dzien(int nr) {
        this.nr = nr;
    }

    public int getNr() {
        return nr;
    }
}

// 15. Metoda main – szybki szablon programu
public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    System.out.println("Podaj liczbę:");
    int n = sc.nextInt();
    System.out.println("Wpisałeś: " + n);
}

// 16. Konwersja String <-> int, double itp.
int x = Integer.parseInt("123");
String s = String.valueOf(123);

// 17. Zapisywanie i odczytywanie obiektów (serializacja)
import java.io.Serializable;

public class Osoba implements Serializable {
    private String imie;
    private int wiek;
}

// 18. Debugowanie – wypisywanie stosu wywołań wyjątku
try {
    // kod
} catch (Exception e) {
    e.printStackTrace();
}

