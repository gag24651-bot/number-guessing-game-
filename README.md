# number-guessing-game-
#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main()
{
    char playAgain;

    // Seed random number generator
    srand(time(0));

    do
    {
        // Generate random number between 1 and 100
        int targetNumber = rand() % 100 + 1;
        int guess;
        int attempts = 0;

        cout << "\n=================================\n";
        cout << "       NUMBER GUESSING GAME\n";
        cout << "=================================\n";
        cout << "I have selected a number between 1 and 100.\n";
        cout << "Try to guess it!\n\n";

        // Guessing loop
        do
        {
            cout << "Enter your guess: ";
            cin >> guess;

            attempts++;

            if (guess > targetNumber)
            {
                cout << "Too High! Try again.\n";
            }
            else if (guess < targetNumber)
            {
                cout << "Too Low! Try again.\n";
            }
            else
            {
                cout << "\nCongratulations! You guessed the number.\n";
                cout << "Number of attempts: " << attempts << endl;

                // Simple score
                int score = 100 - (attempts - 1) * 10;

                if (score < 0)
                    score = 0;

                cout << "Your score: " << score << endl;
            }

        } while (guess != targetNumber);

        // Replay option
        cout << "\nDo you want to play again? (y/n): ";
        cin >> playAgain;

    } while (playAgain == 'y' || playAgain == 'Y');

    cout << "\nThank you for playing!\n";

    return 0;
}