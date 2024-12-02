import java.util.Random;
import java.util.Scanner;

public class PracticalWork6 {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Select a task (1-5):");
        System.out.println("1: Count even and odd numbers in an array");
        System.out.println("2: Check if a polygon can exist based on its angles");
        System.out.println("3: Replace a specific value in an array");
        System.out.println("4: Generate a sine table for angles from 0 to 90 degrees");
        System.out.println("5: Check if an array is sorted in ascending or descending order");

        int choice = scanner.nextInt();
        switch (choice) {
            case 1 -> countEvenAndOdd();
            case 2 -> checkPolygon();
            case 3 -> replaceArrayValue();
            case 4 -> generateSineTable();
            case 5 -> checkArrayOrder();
            default -> System.out.println("Invalid choice. Please select a number between 1 and 5.");
        }
    }

    public static void countEvenAndOdd() {
        int size = 20; // Array size
        int[] array = new int[size];
        Random random = new Random();

        // Generate random numbers
        for (int i = 0; i < size; i++) {
            array[i] = random.nextInt(100); // Random number between 0 and 99
        }

        int evenCount = 0, oddCount = 0;

        // Count even and odd numbers
        for (int num : array) {
            if (num % 2 == 0) {
                evenCount++;
            } else {
                oddCount++;
            }
        }

        // Display results
        System.out.println("Array: ");
        for (int num : array) {
            System.out.print(num + " ");
        }
        System.out.println("\nEven numbers: " + evenCount);
        System.out.println("Odd numbers: " + oddCount);
    }

    public static void checkPolygon() {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of angles (n):");
        int n = scanner.nextInt();
        int[] angles = new int[n];

        System.out.println("Enter the angles:");
        int sum = 0;
        for (int i = 0; i < n; i++) {
            angles[i] = scanner.nextInt();
            sum += angles[i];
        }

        int expectedSum = 180 * (n - 2);
        if (sum == expectedSum) {
            System.out.println("The polygon is valid.");
        } else {
            System.out.println("The polygon is not valid.");
        }
    }

    public static void replaceArrayValue() {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the size of the array:");
        int size = scanner.nextInt();
        int[] array = new int[size];
        Random random = new Random();

        // Generate random numbers
        for (int i = 0; i < size; i++) {
            array[i] = random.nextInt(100);
        }

        // Display the original array
        System.out.println("Original array: ");
        for (int num : array) {
            System.out.print(num + " ");
        }
        System.out.println();

        // Replace value
        System.out.println("Enter the value to find:");
        int target = scanner.nextInt();
        System.out.println("Enter the new value:");
        int newValue = scanner.nextInt();

        for (int i = 0; i < array.length; i++) {
            if (array[i] == target) {
                array[i] = newValue;
            }
        }

        // Display the updated array
        System.out.println("Updated array: ");
        for (int num : array) {
            System.out.print(num + " ");
        }
        System.out.println();
    }

    public static void generateSineTable() {
        System.out.println("Sine table from 0 to 90 degrees:");
        for (int i = 0; i <= 90; i++) {
            System.out.printf("%.4f ", Math.sin(Math.toRadians(i)));
            if (i % 10 == 9) { // Print 10 values per line
                System.out.println();
            }
        }
    }

    public static void checkArrayOrder() {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the size of the array:");
        int size = scanner.nextInt();
        int[] array = new int[size];
        Random random = new Random();

        // Generate random numbers
        for (int i = 0; i < size; i++) {
            array[i] = random.nextInt(100);
        }

        // Display the array
        System.out.println("Array: ");
        for (int num : array) {
            System.out.print(num + " ");
        }
        System.out.println();

        boolean isAscending = true, isDescending = true;

        for (int i = 0; i < array.length - 1; i++) {
            if (array[i] > array[i + 1]) {
                isAscending = false;
            }
            if (array[i] < array[i + 1]) {
                isDescending = false;
            }
        }

        if (isAscending) {
            System.out.println("The array is sorted in ascending order.");
        } else if (isDescending) {
            System.out.println("The array is sorted in descending order.");
        } else {
            System.out.println("The array is not sorted.");
        }
    }
}
