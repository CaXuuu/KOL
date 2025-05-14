package KOL;

import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;
import java.util.Scanner;

public class Main {

    private static final String FILE_PATH = "C:/Users/macie/IdeaProjects/javakol1/src/KOL/test.txt";

    public static void main(String[] args) {
        System.out.println("Podaj jakis tekst");
Scanner scanner = new Scanner(System.in);
String text = scanner.nextLine();
        System.out.println("Podales: "+text);

        try {
            FileWriter fileWriter = new FileWriter(FILE_PATH);
            PrintWriter printWriter = new PrintWriter(fileWriter);
            printWriter.println("Podales: ");
            printWriter.println(text);
            printWriter.close();
        } catch (IOException e) {
            throw new RuntimeException(e);
        }

    }
}
