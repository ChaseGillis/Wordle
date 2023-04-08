"""
Chase Gillis  4/06/23
Wordle
"""

import wordle as w
import random as r

AS = 0
HS = 0
scores=[]
LG = 0

while True:
    allwords = w.words
    wordle = r.choice(allwords)
    wordle = wordle.upper()
    guess = ''
    guesses = []
    x = 0
    #print('The Wordle is', wordle)
    print()
    print(format('WORDLE', '^40s'))            
    print('-'*40)
    #print( len(allwords), "words available." )

    while x != 6 and guess != wordle:
        while True:
            guess = input('Guess the word: ')
            if len(guess) == 5 and guess.isalpha():
                guess = guess.upper()
                break
            elif (not guess.isalpha()):
                print("Invalid word.")
            else:
                print('You must enter a 5 letter word.')
        guesses.append(guess)
        print()
        for i in range(len(guesses)-1):
            print_guess = guesses[i]
            for j in range(5):
                if wordle.find(print_guess[j]) != -1:
                    if wordle[j] == print_guess[j]:
                        print(print_guess[j], '*', sep='', end=' ')
                    else:
                        print(print_guess[j], '?', sep='', end=' ')
                else:
                    print(print_guess[j],'', end=' ')
            print()
        for i in range(5):
            if wordle.find(guess[i]) != -1:
                if wordle[i] == guess[i]:
                    print(guess[i], '*', sep='', end=' ')
                else:
                    print(guess[i], '?', sep='', end = ' ')
            else:
                print(guess[i],'' , end = ' ')
        print()
        x += 1
        if guess == wordle:
            print('Correct! The WORDLE is', wordle)
            print('You guessed the wordle in', len(guesses), 'tries.')
            scores.append(len(guesses))
        elif x == 6:
            print('Sorry, you did not guess the Wordle. The Wordle is', wordle)
            LG += 1
    while True:
        yn = input('Do you want to play again? (Y) or (N) ')
        if yn == 'N' or yn == 'Y' or yn == 'y' or yn == 'n':
            break
        else:
            print('Invalid response.')
    if yn == 'N' or yn == 'n':
        break
if len(scores) == 0:
    print('You have won no games and do not have a high score.')
else:
    HS = min(scores)
    for i in range(len(scores)):
        AS += scores[i]
    AS /= len(scores)
    print('High Score:', HS)
    print('Average Score:', AS)
print('Number of lost games:', LG)
