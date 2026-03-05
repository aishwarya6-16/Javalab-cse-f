## Experiment 11:

## TITLE: 11)Write a JAVA program using Threads for the Train Reservation.

## SOURCE CODE:

```
class Reservation {

    int availableBerths;

    Reservation(int berths) {
        availableBerths = berths;
    }

    synchronized void reserve(String personName, int requestedBerths) {

        System.out.println(personName + " is trying to reserve " + requestedBerths + " berth(s)");

        if (availableBerths >= requestedBerths) {

            System.out.println("Berths available for " + personName);

            availableBerths = availableBerths - requestedBerths;

            System.out.println("Reservation confirmed for " + personName);
            System.out.println("Remaining berths: " + availableBerths);

        } else {

            System.out.println("Reservation failed for " + personName);
            System.out.println("Not enough berths available");

        }

        System.out.println("-----------------------------------");
    }
}
class Person extends Thread {

    Reservation reservation;
    String personName;
    int berthsNeeded;

    Person(Reservation r, String name, int berths) {
        reservation = r;
        personName = name;
        berthsNeeded = berths;
    }

    public void run() {

        reservation.reserve(personName, berthsNeeded);

    }
}
public class Main {

    public static void main(String[] args) {

        Reservation reservation = new Reservation(5);

        Person p1 = new Person(reservation, "Ram", 2);
        Person p2 = new Person(reservation, "Sita", 2);
        Person p3 = new Person(reservation, "Ravi", 2);

        p1.start();
        p2.start();
        p3.start();
    }
}
```
## OUTPUT :
<img width="835" height="494" alt="exp_11_0utput" src="https://github.com/user-attachments/assets/c1ce147a-49fd-4e27-8b8a-9487fcdc62e3" />

