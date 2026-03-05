# Additional-5
# TITLE: Additional-5. ) Java program to implement cricket team
```
import java.util.Scanner;

// Class Cricket
class Cricket {

    String playerName;
    String teamName;
    double battingAverage;

    // Constructor
    Cricket(String playerName, String teamName, double battingAverage) {
        this.playerName = playerName;
        this.teamName = teamName;
        this.battingAverage = battingAverage;
    }

    // Method to display player details
    void display() {
        System.out.println("Player: " + playerName + ", Batting Average: " + battingAverage);
    }
}

// Main class
public class CricketTeam {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        // Input number of players
        System.out.print("Enter number of players: ");
        int n = sc.nextInt();
        sc.nextLine();

        // Create array of Cricket objects
        Cricket[] players = new Cricket[n];

        // Input player details
        for (int i = 0; i < n; i++) {

            System.out.println("Enter details for player " + (i + 1));

            System.out.print("Player Name: ");
            String playerName = sc.nextLine();

            System.out.print("Team Name: ");
            String teamName = sc.nextLine();

            System.out.print("Batting Average: ");
            double avg = sc.nextDouble();
            sc.nextLine();

            players[i] = new Cricket(playerName, teamName, avg);
        }

        // Print players team-wise
        System.out.println("\nPlayers Team-wise:");

        for (int i = 0; i < n; i++) {

            String team = players[i].teamName;

            // Check if this team is already printed
            boolean printed = false;
            for (int j = 0; j < i; j++) {
                if (players[j].teamName.equals(team)) {
                    printed = true;
                    break;
                }
            }

            if (!printed) {
                System.out.println("\nTeam: " + team);

                for (int k = 0; k < n; k++) {
                    if (players[k].teamName.equals(team)) {
                        players[k].display();
                    }
                }
            }
        }

        sc.close();
    }
}
```
## output
<img width="730" height="751" alt="exp_add5_0utput" src="https://github.com/user-attachments/assets/bd42733b-d6a4-4833-aa88-d779e167bc45" />
