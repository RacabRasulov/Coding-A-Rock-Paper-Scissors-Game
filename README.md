ublic class Main {
    public static void main(String[] args) {


            // Get the user input
            Scanner in = new Scanner(System.in);
            //Create score variables
            int wins = 0;
            int losses = 0;
            //Loop thought  and keep asking the user to enter movies
            while (true) {
                System.out.println(
                        "Enter your move.Type in rock,paper or scissors.If you want to exit the game ,type in quit");
                String myMove = in.nextLine();
                //Check if the user entered quit
                if (myMove.equals("quit")) {
                    break;
                }
                //verify that myMove is valid
                if (!myMove.equals("rock") && !myMove.equals("paper") && !myMove.equals("scissors")) {
                    System.out.printf("Your move is not valid!");
                } else {
                    //Randomly generate
                    int rand = (int) (Math.random() * 3);

                    String oppenentMove = "";
                    if (rand == 0) {
                        oppenentMove = "rock";
                    } else if (rand == 1) {
                        oppenentMove = "paper";
                    } else {
                        oppenentMove = "scissors";
                    }
                    System.out.println("OppenentMove " + oppenentMove);
                    //Calculate if the  user won ,lost or tied
                    if (myMove.equals(oppenentMove)) {
                        System.out.println("Your tied!");
                    } else if ((myMove.equals("rock") && oppenentMove.equals("scissors"))
                            || myMove.equals("scissors") && oppenentMove.equals("paper")
                            || myMove.equals("paper") && oppenentMove.equals("rock")) {
                        System.out.printf("You won!");
                        wins++;
                    } else {
                        System.out.printf("You lost!");
                        losses++;
                    }
                }
                // print wins or losses
                System.out.println("You have won" + wins + "games!");
                System.out.println("You have loss" + losses + "games!");
            }
            if (wins > losses) {
                System.out.printf("You won more games than you lost!");
            } else if (wins < losses) {
                System.out.printf("You lost more games than you won!");
            } else {
                System.out.printf("You won and lost  an equal number  of games!");
            }
            System.out.println("Thank you for playing! : ");
        }
    }
