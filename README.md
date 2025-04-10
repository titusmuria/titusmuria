 //  Names: Titus muuria machiuka
 // RegNo: EB3/62553/22
 // Factorial code 
 //using java language

import java.util.Scanner; // Import Scanner for user input

public class Factorial {
    
    // Method to calculate factorial using an iterative approach
    public static long factorial(int n) {
        if (n == 0 || n == 1) { // Base case: 0! = 1 and 1! = 1
            return 1;
        }
        long result = 1; // Variable to store factorial result
        for (int i = 2; i <= n; i++) { // Loop from 2 to n
            result *= i; // Multiply result by current number i
        }
        return result; // Return the computed factorial
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); // Create Scanner object for user input

        // Prompt user for input
        System.out.print("Enter a number: ");
        int num = scanner.nextInt(); // Read an integer from the user
        
        // Check for negative input
        if (num < 0) {
            System.out.println("Factorial is not defined for negative numbers.");
        } else {
            // Call factorial method and display the result
            System.out.println("Factorial of " + num + " is: " + factorial(num));
        }

        scanner.close(); // Close the Scanner to prevent resource leak
    }
}

CALCULATING TIME COMPLEXITY

Operation	         Time Complexity (units)	Times Repeated
if (n == 0		          n == 1)
long result = 1;	      O(1)	                   1
for (int i = 2; i <= n; i++)	O(N)	        Runs N-1 times
result *= i;	         O(1)	                        N-1 times
return result;	       O(1)	                   1


T(n)=1+1+(N−1)+(N−1)+1
T(n)=2N+2
T(n)=2N+2
the final complexity is:
O(N)


FIBONACCI CODE

import java.util.Scanner; // Import Scanner for user input

public class FibonacciCalculator {

    // Iterative method to generate Fibonacci sequence
    public static void fibonacciIterative(int n) {
        long first = 0, second = 1; // Initialize the first two terms
        System.out.print("Fibonacci Sequence (Iterative): " + first + " " + second + " ");

        // Loop to calculate the next terms in the sequence
        for (int i = 2; i < n; i++) { 
            long next = first + second; // Compute the next Fibonacci number
            System.out.print(next + " "); // Print the current term
            first = second; // Update first term
            second = next; // Update second term
        }
        System.out.println(); // Move to a new line after the sequence is printed
    }

    // Recursive method to calculate a Fibonacci number at position n
    public static long fibonacciRecursive(int n) {
        if (n == 0) return 0; // Base case: 0th Fibonacci number is 0
        if (n == 1) return 1; // Base case: 1st Fibonacci number is 1
        return fibonacciRecursive(n - 1) + fibonacciRecursive(n - 2); // Recursively calculate Fibonacci number
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); // Create Scanner object to read user input

        // Get user input
        System.out.print("Enter the number of terms: ");
        int num = scanner.nextInt(); // Read an integer from user

        // Validate user input
        if (num < 1) { // Check if input is valid
            System.out.println("Please enter a positive number.");
        } else {
            // Generate and display Fibonacci sequence using an iterative approach
            fibonacciIterative(num);

            // Generate and display Fibonacci sequence using a recursive approach
            System.out.print("Fibonacci Sequence (Recursive): ");
            for (int i = 0; i < num; i++) {
                System.out.print(fibonacciRecursive(i) + " "); // Print each Fibonacci number recursively
            }
            System.out.println(); // Move to a new line
        }

        scanner.close(); // Close the Scanner object to prevent resource leaks
    }
}

TIME COMPLEXITY CALCULATION
Operation	      Time Complexity	    Times Executed
Variable  
Initialization	      O(1)	            1
Printing first 
two terms	            O(1)	            1
Loop (for i = 2 to n)	O(N)	        (n-2) times
Inside the loop:		
- Compute next	      O(1)	           n-2
- Print next	        O(1)	           n-2
- Update first,
- second	            O(1)	           n-2
Print newline	        O(1)	            1


Total Execution Time
T(n)=1+1+(n−2)+(n−2)+(n−2)+1
T(n)=1+1+(n−2)+(n−2)+(n−2)+1
T(n)=3N−3
T(n)=3N−3
Since we ignore constants, the time complexity is:
O(N)











