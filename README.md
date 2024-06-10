# Guess-the-ball


import random

def generate_random_number(n):
    """Generate a random number between 0 and n."""
    return random.randint(0, n)

def check_guess(cup, g):
    """Check if the user's guess matches the randomly generated number."""
    if cup == g:
        print("Bravo!")
    else:
        print("False")

def main():
    bf, bs = 2, 10
    n = int(input("Enter a number between 2 and 10: "))
    while not (bf <= n <= bs):
        n = int(input("Please enter a number between 2 and 10: "))

    t = [0] * (n+1)
    g = generate_random_number(n)
    t[g] = 1

    # Display the randomly generated number (for testing purposes)
    print("The randomly generated number is:", g)

    for i in range(n+1):
        print(i, end=' ')
    print()

    for i in range(n+1):
        print(t[i], end=' ')
    print()

    while True:
        cup = int(input("Enter your guess (between 0 and {}): ".format(n)))
        if 0 <= cup <= n:
            check_guess(cup, g)
            play_again = input("Do you want to play again? (yes/no): ")
            if play_again.lower() != "yes":
                break
        else:
            print("Please enter a number between 0 and {}.".format(n))

if __name__ == "__main__":
    main()
