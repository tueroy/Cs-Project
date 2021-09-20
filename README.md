import java.util.Scanner;

public class Blackjack {


    public static void main(String[] args) {
        Scanner pick = new Scanner(System.in);
        P1Random rancard = new P1Random();
        int playerCardValue = rancard.nextInt(13) + 1;
        int dealerCardvalue = rancard.nextInt(11) + 16;
        boolean gameover = false;
        int numofgame = 1;
        int numOfWin = 0;
        int numOfL = 0;
        int numOftie = 0;
        int playerhand = 0;
        int dealerhand = 0;
        int numOfWins = 0;

        playerhand += playerCardValue;
        System.out.println("START GAME #" + numofgame);
        System.out.println("Your card is a " + playerhand + "!");
        System.out.println("Your hand is: " + playerhand);
        System.out.println("1.  Get another card");
        System.out.println("2.  Hold hand");
        System.out.println("3.  Print statistics");
        System.out.println("4.  Exit");
        System.out.println("Choose an option: ");

        while(!gameover) {
            int playernewrandom = rancard.nextInt(13)+1;

            double percentage = (double)(numOfWin / numofgame * 100);
            int select = pick.nextInt();

            playerhand += playerCardValue;
            if (select == 1) {//sets of different options user can pick

                String playerhandshow;
                if (playerhand == 21) {

                    if (playerCardValue == 1) {             //sets of unique cards that would be represented with a string, and this would be used for other if cases
                        playerhandshow = "ACE";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("BLACKJACK! You win!");
                        ++numofgame;
                        ++numOfWin;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    } else if (playerCardValue == 11) {
                        playerhand +=10;
                        playerhandshow = "JACK";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("BLACKJACK! You win!");
                        ++numofgame;
                        ++numOfWin;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    } else if (playerCardValue == 12) {
                        playerhand +=10;
                        playerhandshow = "QUEEN";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("BLACKJACK! You win!");
                        ++numofgame;
                        ++numOfWin;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    } else if (playerCardValue == 13) {
                        playerhand +=10;
                        playerhandshow = "KING";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("BLACKJACK! You win!");
                        ++numofgame;
                        ++numOfWin;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    } else {

                        System.out.println("Dealer's hand: " + playerCardValue + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("BLACKJACK! You win!");
                        ++numofgame;
                        ++numOfWin;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);

                        continue;
                    }

                }


                if (playerhand > 21) {                      //After every win or lost, the number of game would increase, and the number of lost or win, or tie would also increase.
                    System.out.println("You exceeded 21! You lose.");
                    ++numofgame;
                    ++numOfL;
                    playerhand = 0;
                    dealerhand = 0;
                    System.out.println("START GAME # " + numofgame);
                    continue;                                  //the continue would run the game again until the user decided to select 4 to exit out of it
                }

                if (playerhand == dealerhand) {
                    if (playerCardValue == 1) {
                        playerhandshow = "ACE";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("It's a tie! No one wins!");
                        ++numofgame;
                        ++numOftie;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    } else if (playerCardValue == 11) {
                        playerhandshow = "JACK";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("It's a tie! No one wins!");
                        ++numofgame;
                        ++numOftie;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    } else if (playerCardValue == 12) {
                        playerhandshow = "QUEEN";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("It's a tie! No one wins!");
                        ++numofgame;
                        ++numOftie;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    } else if (playerCardValue == 13) {
                        playerhandshow = "KING";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("It's a tie! No one wins!");
                        ++numofgame;
                        ++numOftie;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    } else {
                        System.out.println("Dealer's hand: " + dealerhand);
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("It's a tie! No one wins!");
                        ++numofgame;
                        ++numOftie;
                        playerhand = 0;
                        dealerhand = 0;
                        System.out.println("START GAME # " + numofgame);
                    }
                    continue;
                }

                if (playerhand < 21) {
                    if (playerCardValue == 1) {
                        playerhandshow = "ACE";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("1.  Get another card");
                        System.out.println("2.  Hold hand");
                        System.out.println("3.  Print statistics");
                        System.out.println("4.  Exit");
                        System.out.println("Choose an option: ");
                    }

                    if (playerCardValue == 11) {
                        playerhandshow = "JACK";
                        System.out.println("Dealer's hand: " + playernewrandom + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("1.  Get another card");
                        System.out.println("2.  Hold hand");
                        System.out.println("3.  Print statistics");
                        System.out.println("4.  Exit");
                        System.out.println("Choose an option: ");
                    }

                    if (playerCardValue == 12) {
                        playerhandshow = "QUEEN";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("1.  Get another card");
                        System.out.println("2.  Hold hand");
                        System.out.println("3.  Print statistics");
                        System.out.println("4.  Exit");
                        System.out.println("Choose an option: ");
                    }

                    if (playerCardValue == 13) {
                        playerhandshow = "KING";
                        System.out.println("Dealer's hand: " + playerhandshow + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("1.  Get another card");
                        System.out.println("2.  Hold hand");
                        System.out.println("3.  Print statistics");
                        System.out.println("4.  Exit");
                        System.out.println("Choose an option: ");
                    } else {
                        System.out.println("Your card is a " + playerCardValue + "!");
                        System.out.println("Your hand is: " + playerhand);
                        System.out.println("1.  Get another card");
                        System.out.println("2.  Hold hand");
                        System.out.println("3.  Print statistics");
                        System.out.println("4.  Exit");
                        System.out.println("Choose an option: ");
                    }
                }
            }

            if (select == 2) {          //selecting option 2 would perform similar to option 1, but we would have the dealer hand's value.
                dealerhand += dealerCardvalue;      //Different cases such as the dealer win or lose or tie is also depicted with an if function
                if (dealerhand > 21) {
                    System.out.println("You win!");
                    ++numofgame;
                    ++numOfWin;
                    playerhand = 0;
                    dealerhand = 0;
                    System.out.println("START GAME # " + numofgame);
                    continue;
                }

                if (dealerhand == 21) {
                    System.out.println("Dealer's hand: " + dealerhand);
                    System.out.println("Your hand is: " + playerhand);
                    System.out.println("Dealer wins!");
                    ++numofgame;
                    ++numOfL;
                    playerhand = 0;
                    dealerhand = 0;
                    System.out.println("START GAME # " + numofgame);
                    continue;
                }

                if (playerhand == dealerhand) {
                    System.out.println("Dealer's hand: " + dealerhand);
                    System.out.println("Your hand is: " + playerhand);
                    System.out.println("It's a tie! No one wins!");
                    ++numofgame;
                    ++numOftie;
                    playerhand = 0;
                    dealerhand = 0;
                    System.out.println("START GAME # " + numofgame);
                    continue;
                }

                if (dealerhand < 21) {
                    System.out.println("Dealer's hand: " + dealerhand);
                    System.out.println("Your hand is: " + playerhand);
                    System.out.println("1.  Get another card");
                    System.out.println("2.  Hold hand");
                    System.out.println("3.  Print statistics");
                    System.out.println("4.  Exit");
                    System.out.println("Choose an option: ");
                }
            }

            if (select == 3) {              //Option 3 simply prints out all the statistic that has been adding up throughout the loop
                System.out.println("Number of Player wins: " + numOfWins);
                System.out.println("Number of Dealer wins: " + numOfL);
                System.out.println("Number of tie games: " + numOftie);
                System.out.println("Total # of games played is: " + numofgame);
                System.out.println("Percentage of Player wins: " +percentage+ " %");
            }

            if (select != 1 && select != 2 && select != 3 && select != 4) {
                System.out.println("Invalid input!");
                System.out.println("Please enter an integer value between 1 and 4.");
            }

            if (select == 4) {      //Option 4 simplys closes the game

                break;
            }
        }

    }
}
