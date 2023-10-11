import java.util.Scanner;

public class SimpCal {
    public static void main(String[] args) {
        Scanner a = new Scanner(System.in);
        System.out.println("Enter the first number:");
        int firstNumber = a.nextInt();
        System.out.println("Enter the second number:");
        int secondNumber = a.nextInt();
        System.out.println("Enter the operation to be performed i.e. '+', '-', '*', or '/'");
        char operator = a.next().charAt(0);

        int output = 0; // Initialize the 'output' variable

        try {
            // Using a switch statement to perform different operations based on the operator
            switch (operator) {
                case '-':
                    output = firstNumber - secondNumber; // Subtract if the operator is '-'
                    break;
                case '+':
                    output = firstNumber + secondNumber; // Add if the operator is '+'
                    break;
                case '*':
                    output = firstNumber * secondNumber; // Multiply if the operator is '*'
                    break;
                case '/':
                    if (secondNumber != 0) {
                        output = firstNumber / secondNumber; // Divide if the operator is '/' (checking for division by zero)
                    } else {
                        System.out.println("Division by zero is not allowed.");
                        return;
                    }
                    break;
                default:
                    System.out.println("Invalid operator.");
                    return; // Invalid operator, exit the program
            }
        } catch (Exception e) {
            System.out.println("An error occurred during the operation.");
            return; // Handle any exceptions that may occur
        }

        // Print the calculated output
        System.out.println("The Required output is: " + output);
    }
}
