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
