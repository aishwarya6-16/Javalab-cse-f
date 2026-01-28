# Additional3
# TITLE: Additional-3. ) Java program to determine if a given string is palindrome or not
```
import java.util.Scanner;

class Palindrome {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the string: ");
        String str = sc.nextLine();

        int start = 0;
        int end = str.length() - 1;
        boolean flag = true;

        while (start < end) {

            if (str.charAt(start) != str.charAt(end)) {
                flag = false;
                break;
            }

            start++;
            end--;
        }

        if (flag) {
            System.out.println("String is a palindrome");

        }
    }
}
```
# output
![screenshot](exp_additional-3.png)
