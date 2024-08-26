# Selenium_First_Test
{
package org.example;

import io.github.bonigarcia.wdm.WebDriverManager;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

import java.util.Scanner;
public class Main {
    public static void main(String[] args) {

        WebDriverManager.chromedriver().setup();    // Chrome sürücüsünü kurar
        WebDriver driver = new ChromeDriver();      // Chrome sürücüsü tipinde bir değişken oluşturur

        Scanner scanner = new Scanner(System.in);

        System.out.print("Url adresini yazınız  :");
        String baseURL = scanner.nextLine();                        // Kullanıcıdan başlık testi için url adresi alır
        System.out.print("Beklenen başlık değerini giriniz  :");
        String expectedData = scanner.nextLine();                   // Kullanıcıdan beklenen başlık değerini alır

        driver.get(baseURL);       // Tarayıcıyı açıp kullanıcının verdiği url adresini açar

        String actualData = driver.getTitle();    // Değişken oluşturduk ve site başlığını değişkene atar

        if(expectedData.equals(actualData)){    // Değerlerin eşitliğini kontrol eder
            System.out.print("Test Passed.");
        }
        else{
            System.out.print("Test Failed.");
        }

        driver.quit();                              // Uygulamayı kapatır

    }
}
}
