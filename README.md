#include <iostream>
#include <cstdlib>  
#include <ctime>    

int main() {

    std::srand(static_cast<unsigned int>(std::time(nullptr)));
    
    int randomNumber = std::rand() % 100 + 1;
    int guess = 0;
    int numberOfGuesses = 0;

    std::cout << "Welcome to the Number Guessing Game!" << std::endl;
    std::cout << "I have selected a number between 1 and 100. Try to guess it!" << std::endl;

    while (true) {
        std::cout << "Enter your guess: ";
        std::cin >> guess;
        numberOfGuesses++;

        if (guess > randomNumber) {
            std::cout << "Too high! Try again." << std::endl;
        } else if (guess < randomNumber) {
            std::cout << "Too low! Try again." << std::endl;
        } else {
            std::cout << "Congratulations! You guessed the correct number: " << randomNumber << std::endl;
            std::cout << "It took you " << numberOfGuesses << " guesses." << std::endl;
            break;
        }
    }

    return 0;
}
