# EXPERIMENT 7

## EXPERIMENT 7A

### TITLE: Creation for User Defined Exception

#### SOURCE CODE:

---

##### InvalidCountryExample java 

```

// User Defined Exception Class
class InvalidCountryException extends Exception {

    // No-argument constructor
    public InvalidCountryException() {
        super();
    }

    // Constructor with message
    public InvalidCountryException(String message) {
        super(message);
    }
}

```

##### UserRegistration java

```

// Main Class
public class UserRegistration {

    // Method to register user
    public void registerUser(String userName, String userCountry)
            throws InvalidCountryException {

        if (!userCountry.equalsIgnoreCase("India")) {
            // Throw custom exception
            throw new InvalidCountryException(
                    "User outside India cannot be registered");
        } else {
            System.out.println("User registration done successfully");
        }
    }

    // Main Method
    public static void main(String[] args) {

        UserRegistration ur = new UserRegistration();

        // Test Case 1: User from USA
        try {
            ur.registerUser("Ravi", "USA");
        } catch (InvalidCountryException e) {
            System.out.println(e.getMessage());
        }

        // Test Case 2: User from India
        try {
            ur.registerUser("Anita", "India");
        } catch (InvalidCountryException e) {
            System.out.println(e.getMessage());
        }
    }
}

```

## OUTPUT:

<img width="542" height="105" alt="exp_7a_0utput" src="https://github.com/user-attachments/assets/dd082a0b-dfb9-4f9d-9655-06e71dc39a25" />


## EXPERIMENT 7B

### TITLE: TestThreads

#### SOURCE CODE:

```

// First Thread - Prints "Good Morning" every 1 second
class GoodMorningThread extends Thread {

    @Override
    public void run() {
        try {
            while (true) {
                System.out.println("Good Morning");
                Thread.sleep(1000);   // 1 second
            }
        } catch (InterruptedException e) {
            System.out.println("GoodMorningThread Interrupted");
        }
    }
}

// Second Thread - Prints "Hello" every 2 seconds
class HelloThread extends Thread {

    @Override
    public void run() {
        try {
            while (true) {
                System.out.println("Hello");
                Thread.sleep(2000);   // 2 seconds
            }
        } catch (InterruptedException e) {
            System.out.println("HelloThread Interrupted");
        }
    }
}

// Third Thread - Prints "Welcome" every 3 seconds
class WelcomeThread extends Thread {

    @Override
    public void run() {
        try {
            while (true) {
                System.out.println("Welcome");
                Thread.sleep(3000);   // 3 seconds
            }
        } catch (InterruptedException e) {
            System.out.println("WelcomeThread Interrupted");
        }
    }
}

// Main Class
public class TestThreads {

    public static void main(String[] args) {

        // Create thread objects
        GoodMorningThread t1 = new GoodMorningThread();
        HelloThread t2 = new HelloThread();
        WelcomeThread t3 = new WelcomeThread();

        // Start all threads
        t1.start();
        t2.start();
        t3.start();
    }
}

```

## OUTPUT:
<img width="322" height="249" alt="exp_7b_0utput" src="https://github.com/user-attachments/assets/5d2b2fc9-2002-4c32-92c4-334dec5e3f93" />


## EXPERIMENT 7C

### TITLE: Illustrating is Alive And join

#### SOURCE CODE:

```

// Class that simulates a long-running task
class LongRunningTask extends Thread {

    @Override
    public void run() {
        try {
            System.out.println("Long running task started...");

            // Simulate 5 seconds of work
            for (int i = 1; i <= 5; i++) {
                System.out.println("Working... " + i);
                Thread.sleep(1000);   // 1 second delay
            }

            System.out.println("Long running task completed!");
        } catch (InterruptedException e) {
            System.out.println("Thread was interrupted.");
        }
    }
}

// Main class
public class ThreadDemo {

    public static void main(String[] args) {

        // Create thread object
        LongRunningTask task1 = new LongRunningTask();

        // Check isAlive() before starting
        System.out.println("Before starting task1: " + task1.isAlive());

        // Start the thread
        task1.start();

        // Check isAlive() after starting
        System.out.println("After starting task1: " + task1.isAlive());

        try {
            System.out.println("Main thread waiting for task1 to complete using join()...");

            // Main thread waits for task1 to finish
            task1.join();

        } catch (InterruptedException e) {
            System.out.println("Main thread interrupted.");
        }

        // Check isAlive() after join()
        System.out.println("After join(): " + task1.isAlive());

        System.out.println("Main thread continues after task1 completed.");
    }
}

```

## OUTPUT:
<img width="606" height="262" alt="exp_7c_0utput" src="https://github.com/user-attachments/assets/7736b58e-3f8e-4922-9b11-48a00cfaf97d" />
