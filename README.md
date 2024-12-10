import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Введіть розмір масиву: ");
        int n = scanner.nextInt();

        int[] arr = new int[n];
        Random rand = new Random();

        for (int i = 0; i < n; i++) {
            arr[i] = rand.nextInt(50); 
        }

        System.out.println("Масив: ");
        for (int i = 0; i < n; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();

        boolean isIncreasing = true;
        boolean isDecreasing = true;

        for (int i = 0; i < n - 1; i++) {
            if (arr[i] >= arr[i + 1]) {
                isIncreasing = false;
            }
            if (arr[i] <= arr[i + 1]) {
                isDecreasing = false;
            }
        }

        if (isIncreasing) {
            System.out.println("Масив зростає.");
        } else if (isDecreasing) {
            System.out.println("Масив спадає.");
        } else {
            System.out.println("Масив не є строго зростаючим або спадним.");
        }
    }
}
