# Number-Guessing-Game....-
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
        int target = rand() % 100 + 1;
        int guess;
        int attempts = 0;

        cout << "\n====================================\n";
        cout << "       NUMBER GUESSING GAME\n";
        cout << "====================================\n";
        cout << "I have selected a number between 1 and 100.\n";
        cout << "Try to guess it!\n\n";

        // Guessing loop
        do
        {
            cout << "Enter your guess: ";
            cin >> guess;

            // Count attempts
            attempts++;

            if (guess > target)
            {
                cout << "Too High! Try a smaller number.\n";
            }
            else if (guess < target)
            {
                cout << "Too Low! Try a larger number.\n";
            }
            else
            {
                cout << "\nCongratulations! You guessed the number!\n";
                cout << "The correct number was: " << target << endl;
                cout << "Number of attempts: " << attempts << endl;

                // Score calculation
                int score = 100 - (attempts - 1) * 10;

                if (score < 0)
                    score = 0;

                cout << "Your Score: " << score << "/100\n";
            }

        } while (guess != target);

        // Replay option
        cout << "\nDo you want to play again? (Y/N): ";
        cin >> playAgain;

    } while (playAgain == 'Y' || playAgain == 'y');

    cout << "\nThank you for playing!\n";
    cout << "Goodbye!\n";

    return 0;
}