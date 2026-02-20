# EXPERIMENT-5
## TITLE : 5a.) Java program to implement Interface 
```java

interface Sortable {
    void sort(int arr[]);
}
class BubbleSort implements Sortable {
    public void sort(int arr[]) {
        int size = arr.length;
        int temp;
        for (int i = 0; i < size - 1; i++) {
            for (int j = 0; j < size - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {   
                    temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
}
 }
}
}
}
class SelectionSort implements Sortable {
    public void sort(int arr[]) {
        int size = arr.length;
        for (int i = 0; i < size - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < size; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
           int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }
}
public class TestSort {
    static void display(int arr[]) {
        for (int item : arr) {
            System.out.print(item + " ");
        }
        System.out.println();
    }
    public static void main(String args[]) {
        int a[] = {8, 9, 10, 4, 3, 2, 1};
        int b[] = {10, 11, 12, 4, 5, 6, 7, 8};
        Sortable s;
        s = new BubbleSort();
        s.sort(a);
        System.out.println("Bubble Sort:");
        display(a);
        s = new SelectionSort();
        s.sort(b);
        System.out.println("Selection Sort:");
        display(b);
    }
}

```
## OUTPUT :

<img width="385" height="88" alt="exp_5a_0utput" src="https://github.com/user-attachments/assets/6a3b2c12-fda2-4fcd-ac18-1aa6eea5b17c"/>


## TITLE: 5b.) Java program to implement Runtime Polymorphism
```java// Parent Class
class Vehicle {
    void run() {
        System.out.println("Vehicle is running");
    }
}
class Car extends Vehicle {
    void run() {
        System.out.println("Car is running");
    }
}
class Bike extends Vehicle {
    void run() {
        System.out.println("Bike is running");
    }
}
public class TestVehicle {
    public static void main(String args[]) {
        Vehicle v;   
        v = new Car();    
        v.run();
        v = new Bike();    
        v.run();
       v = new Vehicle(); 
        v.run();
    }
}
```

## OUTPUT :

<img width="382" height="80" alt="exp_5b_0utput" src="https://github.com/user-attachments/assets/87ea2fc2-fd25-498d-b922-bda368aba971" />


## TITLE : 5c.) Java program using StringBuffer to delete a character
```java
public class DeleteChars {
    public static void main(String args[]) {
        StringBuffer sb = new StringBuffer("Java Programming");
        System.out.println("Original String: " + sb);
        sb.deleteCharAt(4);
        System.out.println("After deleting character at index 4: " + sb);
        sb.delete(0, 4);
        System.out.println("After deleting characters from index 0 to 4: " + sb);
    }
}
```

## OUTPUT :

<img width="468" height="79" alt="exp_5c_0utput" src="https://github.com/user-attachments/assets/25ad9012-4bed-4206-9072-1f51ae54f060" />

