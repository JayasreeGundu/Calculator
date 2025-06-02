# Calculator
import java.util.Scanner;

public class Calculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean continueCalc = true;

        while (continueCalc) {
            System.out.println("\n=== Calculator Menu ===");
            System.out.println("1. Addition");
            System.out.println("2. Subtraction");
            System.out.println("3. Multiplication");
            System.out.println("4. Division");
            System.out.println("5. Exit");
            System.out.print("Choose an operation: ");
            
            int choice = scanner.nextInt();
            switch (choice) {
			case 1: // Addition
                    System.out.print("Enter number of values to add: ");
                    int addCount = scanner.nextInt();
                    double sum = 0;
                    for (int i = 0; i < addCount; i++) {
                        System.out.print("Enter number " + (i + 1) + ": ");
                        sum += scanner.nextDouble();
                    }
                    System.out.println("Result = " + sum);
                    break;

                case 2: // Subtraction
                    System.out.print("Enter number of values to subtract: ");
                    int subCount = scanner.nextInt();
                    if (subCount < 1) {
                        System.out.println("Need at least one number.");
                        break;
                    }
                    System.out.print("Enter number 1: ");
                    double result = scanner.nextDouble();
                    for (int i = 1; i < subCount; i++) {
                        System.out.print("Enter number " + (i + 1) + ": ");
                        result -= scanner.nextDouble();
                    }
                    System.out.println("Result = " + result);
                    break;

                case 3: // Multiplication
                    System.out.print("Enter number of values to multiply: ");
                    int mulCount = scanner.nextInt();
                    double product = 1;
                    for (int i = 0; i < mulCount; i++) {
                        System.out.print("Enter number " + (i + 1) + ": ");
                        product *= scanner.nextDouble();
                    }
                    System.out.println("Result = " + product);
                    break;

                case 4: // Division
                    System.out.print("Enter number of values to divide: ");
                    int divCount = scanner.nextInt();
                    if (divCount < 1) {
                        System.out.println("Need at least one number.");
                        break;
                    }
                    System.out.print("Enter number 1: ");
                    double quotient = scanner.nextDouble();
                    for (int i = 1; i < divCount; i++) {
                        System.out.print("Enter number " + (i + 1) + ": ");
                        double next = scanner.nextDouble();
                        if (next == 0) {
                            System.out.println("Division by zero is not allowed.");
                            break;
                        }
                        quotient /= next;
                    }
                    System.out.println("Result = " + quotient);
                    break;

                case 5:
                    continueCalc = false;
                    System.out.println("Exiting calculator. Goodbye!");
                    break;

                default:
                    System.out.println("Invalid choice. Please choose again.");
            }
        }

        scanner.close();
    }
}
