# EXPERIMENT 6

## EXPERIMENT 6A

### TITLE: Expection handling mechanism.

#### SOURCE CODE:

```

import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        // Read size of array
        System.out.print("Enter size of array: ");
        int n = sc.nextInt();

        // Create array
        int[] arr = new int[n];

        // Read array elements
        System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        // Ask user for index
        System.out.print("Enter index to access: ");
        int index = sc.nextInt();

        // Exception handling
        try {
            System.out.println("Element at index " + index + " is: " + arr[index]);
        } 
        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Invalid index! Please enter index between 0 and " + (n - 1));
        }

        sc.close();
    }
}

```

## OUTPUT

<img width="425" height="93" alt="exp_6a_0utput" src="https://github.com/user-attachments/assets/7e97ce8f-163f-48a2-b2c8-aa0214250b6d" />


## EXPERIMENT 6B

### TITLE: Multiple catch clauses

#### SOURCE CODE:

```

import java.util.Scanner;
import java.util.InputMismatchException;

public class MultipleCatchExample {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        // Creating an integer array
        int arr[] = {10, 20, 30, 40, 50};

        try {
            // Taking two numbers from user
            System.out.print("Enter first number: ");
            int a = sc.nextInt();

            System.out.print("Enter second number: ");
            int b = sc.nextInt();

            // Division operation
            int result = a / b;
            System.out.println("Result of division: " + result);

            // Accessing array element
            System.out.print("Enter index to access array element: ");
            int index = sc.nextInt();

            System.out.println("Element at index " + index + " = " + arr[index]);
        }

        catch (ArithmeticException e) {
            System.out.println("Error: Division by zero is not allowed.");
        }

        catch (InputMismatchException e) {
            System.out.println("Error: Please enter numeric values only.");
        }

        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Error: Invalid array index.");
        }

        catch (Exception e) {
            System.out.println("Some other error occurred.");
        }

        finally {
            System.out.println("Program continues...");
            sc.close();
        }
    }
}

```

## OUTPUT
<img width="462" height="112" alt="exp_6b_0utput" src="https://github.com/user-attachments/assets/ab0a5478-8d90-4eb6-8296-ade0bc813f13" />



## EXPERIMENT 6C

### TITLE: Creation of java Bulit-in-Expection.

#### SOURCE CODE:

```

import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        try {
            // ArithmeticException (Divide by zero)
            System.out.print("Enter an integer to divide 100: ");
            int n = sc.nextInt();
            int result = 100 / n;
            System.out.println("Result: " + result);

            // ArrayIndexOutOfBoundsException
            int[] arr = new int[3];
            System.out.println("Accessing element at index 5:");
            System.out.println(arr[5]);

            // NumberFormatException
            System.out.print("Enter a number as text: ");
            String s = sc.next();
            int num = Integer.parseInt(s);
            System.out.println("Converted number: " + num);
        }

        catch (ArithmeticException e) {
            System.out.println("ArithmeticException: Division by zero.");
        }

        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ArrayIndexOutOfBoundsException: Invalid index.");
        }

        catch (NumberFormatException e) {
            System.out.println("NumberFormatException: Invalid numeric format.");
        }

        catch (Exception e) {   // Optional general exception
            System.out.println("Some other exception occurred.");
        }

        System.out.println("Program continues...");
        sc.close();
    }
}

```

## OUTPUT
<img width="457" height="100" alt="exp_6c_0utput" src="https://github.com/user-attachments/assets/d9058810-6ab2-4380-935e-ec34c8242bda" />


