# EXPERIMENT 8

## EXPERIMENT 8A

### TITLE: a) Write a Program illustrating Daemon Threads.

#### SOURCE CODE:

```

// DaemonThread class
class DaemonThread extends Thread {

    // Overriding run() method
    @Override
    public void run() {
        try {
            // Loop runs continuously
            while (true) {
                System.out.println("Daemon thread running");
                Thread.sleep(500);   // Sleep for 500 milliseconds
            }
        } catch (InterruptedException e) {
            System.out.println("Daemon thread interrupted");
        }
    }
}

// UserThread class
class UserThread extends Thread {

    // Overriding run() method
    @Override
    public void run() {
        try {
            // Loop from 1 to 5
            for (int i = 1; i <= 5; i++) {
                System.out.println("User thread iteration: " + i);
                Thread.sleep(1000);   // Sleep for 1000 milliseconds
            }
        } catch (InterruptedException e) {
            System.out.println("User thread interrupted");
        }
    }
}

// Main class
public class TestDaemon {

    public static void main(String[] args) {

        // Creating UserThread object
        UserThread userThread = new UserThread();

        // Creating DaemonThread object
        DaemonThread daemonThread = new DaemonThread();

        // Setting daemon thread
        daemonThread.setDaemon(true);

        // Starting both threads
        userThread.start();
        daemonThread.start();

        // Main thread ends here
        System.out.println("Main thread execution completed");
    }
}

```

## OUTPUT
<img width="943" height="586" alt="exp_8a_0utput" src="https://github.com/user-attachments/assets/88aa1faf-b621-4e0b-bcb1-d3888aa19ae1" />


## EXPIREMENT 8B

### TITLE:b) Write a JAVA program Producer Consumer Problem

#### SOURCE CODE:

```

// Buffer class (Shared Resource)
class Buffer {

    int[] buffer;
    int count = 0;
    int in = 0;
    int out = 0;

    Buffer(int size) {
        buffer = new int[size];
    }

    // Method to produce item
    synchronized void produce(int item) {
        try {

            // If buffer is full, wait
            while (count == buffer.length) {
                wait();
            }

            buffer[in] = item;
            in = (in + 1) % buffer.length;
            count++;

            notify(); // Notify consumer

        } catch (Exception e) {
            System.out.println(e);
        }
    }

    // Method to consume item
    synchronized int consume() {
        int item = 0;

        try {

            // If buffer empty, wait
            while (count == 0) {
                wait();
            }

            item = buffer[out];
            out = (out + 1) % buffer.length;
            count--;

            notify(); // Notify producer

        } catch (Exception e) {
            System.out.println(e);
        }

        return item;
    }
}


// Producer class
class Producer extends Thread {

    Buffer buffer;

    Producer(Buffer buffer) {
        this.buffer = buffer;
    }

    public void run() {

        for (int i = 1; i <= 10; i++) {
            buffer.produce(i);
            System.out.println("Produced: " + i);
        }
    }
}


// Consumer class
class Consumer extends Thread {

    Buffer buffer;

    Consumer(Buffer buffer) {
        this.buffer = buffer;
    }

    public void run() {

        for (int i = 1; i <= 10; i++) {
            int item = buffer.consume();
            System.out.println("Consumed: " + item);
        }
    }
}


// Main class
public class ProducerConsumer {

    public static void main(String[] args) {

        Buffer buffer = new Buffer(5);

        Producer p = new Producer(buffer);
        Consumer c = new Consumer(buffer);

        p.start();
        c.start();
    }
}

```

## OUTPUT:
<img width="923" height="730" alt="exp_8b_0utput" src="https://github.com/user-attachments/assets/25eed448-bafb-4125-9448-7591af5c6b66" />


## EXPERIMENT 8C

### TITLE:c) Write a JAVA program that import and use the user defined packages 

#### SOURCE CODE:

---

##### Arthimmeticoperations.java

```

// ArithmeticOperations.java

package arithmetic;

// Class inside arithmetic package
public class ArithmeticOperations {

    // Method for addition
    public int addition(int x, int y) {
        return x + y;
    }

    // Method for subtraction
    public int subtraction(int x, int y) {
        return x - y;
    }

    // Method for multiplication
    public int multiplication(int x, int y) {
        return x * y;
    }

    // Method for division
    public int division(int x, int y) {
        return x / y;
    }
}

```

##### calculation.java

```

// Calculate.java

import arithmetic.*;   // Importing user defined package

public class Calculate {

    public static void main(String[] args) {

        // Creating object of ArithmeticOperations
        ArithmeticOperations ao = new ArithmeticOperations();

        int sum = ao.addition(10, 5);
        System.out.println("Addition: " + sum);

        int diff = ao.subtraction(10, 5);
        System.out.println("Subtraction: " + diff);

        int prod = ao.multiplication(10, 5);
        System.out.println("Multiplication: " + prod);

        int quot = ao.division(10, 5);
        System.out.println("Division: " + quot);
    }
}
```

---

## OUTPUT:
<img width="274" height="123" alt="exp_8c_0utput" src="https://github.com/user-attachments/assets/eb57ace7-f8a7-4e8a-b463-094e6e54556f" />

