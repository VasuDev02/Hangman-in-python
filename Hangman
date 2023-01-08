import random
from words import words
import string

def valid_words(words):
    word=random.choice(words)
    while '-' in word or ' ' in word:
        word=random.choice(words)
    return word.upper()

def hangman():
    word=valid_words(words)
    alphabets=set(string.ascii_uppercase)
    used=set()
    word_letters=set(word)
    lives=7
    while lives>0 and len(word_letters)>0:
        print('you have %d lives left'%lives)
        print('you have used this letters:',' '.join(used))
        correct_letters = [letter if letter in used else '_' for letter in word]
        print('current word  :',' '.join(correct_letters))
        user = input("Guess the letter:\n").upper()
        if user in used:
            print('you have already used this letter try again..')
        elif user in alphabets-used:
            used.add(user)
            alphabets.remove(user)
            if user in word_letters:
                word_letters.remove(user)
            else:
                lives=lives-1
                print('you letter ',user,' is not in the word')
        else:
            print('invalid character..')
            print('please enter a alphabet')
            lives=lives-1
    if lives==0:
        print("sorry you died")
        print('The correct word is',word)
    else:
        print("Yay!,you Guessed the word correctly...",word)


hangman()



