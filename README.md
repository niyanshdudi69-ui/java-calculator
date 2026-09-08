import java.util.Scanner;

public class Calculator {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.println("=================================");
        System.out.println("       Welcome to Calculator     ");
        System.out.println("=================================");

        while (true) {

            System.out.println("\nChoose an operation:");
            System.out.println("1. Addition (+)");
            System.out.println("2. Subtraction (-)");
            System.out.println("3. Multiplication (*)");
            System.out.println("4. Division (/)");
            System.out.println("5. Exit");

            System.out.print("\nEnter your choice: ");

            int choice;

            try {
                choice = scanner.nextInt();
            } catch (Exception e) {
                System.out.println("Please enter a valid number.");
                scanner.nextLine();
                continue;
            }

            if (choice == 5) {
                System.out.println("\nThank you for using Calculator. Goodbye! ");
                break;
            }

            if (choice < 1 || choice > 5) {
                System.out.println(" Invalid choice. Please select 1-5.");
                continue;
            }

            System.out.print("Enter first number: ");
            double firstNumber = scanner.nextDouble();

            System.out.print("Enter second number: ");
            double secondNumber = scanner.nextDouble();

            double result;

            switch (choice) {
                case 1:
                    result = firstNumber + secondNumber;
                    break;

                case 2:
                    result = firstNumber - secondNumber;
                    break;

                case 3:
                    result = firstNumber * secondNumber;
                    break;

                case 4:
                    if (secondNumber == 0) {
                        System.out.println(" Cannot divide by zero.");
                        continue;
                    }
                    result = firstNumber / secondNumber;
                    break;

                default:
                    System.out.println(" Invalid operation.");
                    continue;
            }

            System.out.println("\n---------------------------------");
            System.out.println("Result: " + result);
            System.out.println("---------------------------------");
        }

        scanner.close();
    }
}

