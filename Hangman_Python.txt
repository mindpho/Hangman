import random 
from words import words


intro = input("Hi there! Are you ready to play hangman? (Y/N) ").upper()
if intro == "Y":
    print("Great! Let's play.")
    print("\n-|--------")
    print("-|        ")
    print("-|        ")
    print("-|        ")
    print("-|^^^^^^^^")
    def hangman():
        word = random.choice(words)
        print("\nThis word has", len(word), "letters.")
        print("\nYou have 6 lives in total.") 
        print(word.replace(word, "-" * len(word)))
        secret_word = set(word)
        lives = 6
        guessed = set()
        while lives > 0 and len(secret_word) > 0:
            user_guess = input("\nGuess a letter: ")
            guessed.add(user_guess)
            print("\nUsed letters: ", " ".join(guessed))
            used = [letter if letter in guessed else '-' for letter in word]
            if user_guess in secret_word:
                print("\nGood job! Keep going: ", " ".join(used))
                
            else:
                print("\nSorry! Try again: ", " ".join(used))
                lives = lives - 1
                if lives == 6:
                    print("\nYou have",lives,"lives left.")
                    print("-|--------")
                    print("-|        ")
                    print("-|        ")
                    print("-|        ")
                    print("-|^^^^^^^^")
                elif lives == 5:
                    print("\nYou have",lives,"lives left.")
                    print("-|--------")
                    print("-|    O   ")
                    print("-|        ")
                    print("-|        ")
                    print("-|^^^^^^^^")
                elif lives == 4:
                    print("\nYou have",lives,"lives left.")
                    print("-|--------")
                    print("-|    O   ")
                    print("-|    |   ")
                    print("-|        ")
                    print("-|^^^^^^^^")
                elif lives == 3:
                    print("\nYou have",lives,"lives left.")
                    print("-|--------")
                    print("-|    O   ")
                    print("-|   /|   ")
                    print("-|        ")
                    print("-|^^^^^^^^")
                elif lives == 2:
                    print("\nYou have",lives,"lives left.")
                    print("-|--------")
                    print("-|    O   ")
                    print("-|   /|\  ")
                    print("-|        ")
                    print("-|^^^^^^^^")
                elif lives == 1:
                    print("\nYou have",lives,"lives left.")
                    print("-|--------")
                    print("-|    O   ")
                    print("-|   /|\  ")
                    print("-|   /    ")
                    print("-|^^^^^^^^")
                elif lives == 0:
                    print("\nYou have",lives,"lives left.")
                    print("-|--------")
                    print("-|    O   ")
                    print("-|   /|\  ")
                    print("-|   / \  ")
                    print("-|^^^^^^^^")
                    print("\nYOU LOST! The secret word is:", word)
        
            if list(word) == used:
                    print("\nYOU WON! The secret word is:", word)
                    break
            
    hangman()
    
         
else:
    print("\nPlease come back when you want to play.")


    

