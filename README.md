using System;

namespace GuessTheNumber
{
    class Program
    {
        static void Main(string[] args)
        {
            Random random = new Random();
            int randomNumber = random.Next(1, 101); // Random number between 1 and 100
            int guess = 0;

            Console.WriteLine("Welcome to Guess the Number!");
            Console.WriteLine("I have chosen a number between 1 and 100. Can you guess it?");

            while (guess != randomNumber)
            {
                Console.Write("Enter your guess: ");
                string input = Console.ReadLine();

                if (int.TryParse(input, out guess))
                {
                    if (guess < randomNumber)
                    {
                        Console.WriteLine("Too low! Try again.");
                    }
                    else if (guess > randomNumber)
                    {
                        Console.WriteLine("Too high! Try again.");
                    }
                    else
                    {
                        Console.WriteLine("Congratulations! You guessed the correct number!");
                    }
                }
                else
                {
                    Console.WriteLine("Please enter a valid number.");
                }
            }
        }
    }
}
