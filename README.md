# python-hangman-game
. It's a simple game in which the player needs to guess the word.    *The word to guess is represented by a row of dashes.   *If the player guesses a letter which exists in the word, the code writes it in all its correct positions.   *The code displays the number of letters guessed by the player and the number of letters yet to be guessed.  *When all the letters entered by the user match with the string to be guessed, a message "Word has been guessed" is displayed.
import random
answerlist=["world"]
#string which we are trying to guess
answer=list(answerlist[0])

#empty list called display
display=[]

#adds the variable answer to display
display.extend(answer)

#this will contain the letters which are yet to be guessed
used=[]

#adds what is in display i.e. the answer to be used
#so we can take the letters out which have been already guessed
used.extend(display)

#iterates through the list 'display'
for i in range(len(display)):
        #replaces each index in the list with '_' 
	display[i]="_"

#the join command puts a space between each '_'
print(' '.join(display))
print()
	
#counter stops the game once all letters have been guessed
count=0

#keeps asking the user until all letters guessed
while count < len(answer):
        guess=input("Please guess a letter")
        guess=guess.lower()

        #iterates through the letter in answer	
        for i in range(len(answer)):
            #if the guessed letter matches a letter in the answer
            if answer[i]==guess and guess in used:
                #replace the index of that guess with the actual letter they guessed
                display[i]=guess
                count=count+1

                #print(used)
                used.remove(guess)

                if guess not in display:
                    print("Sorry, wrong guess")
                else:
                    print("You have guessed:",count,"correct letters.")
                    print("You need to guesss",len(answer)-count,"more letters.")

                #print out the new string with guessed letters   
                print(' '.join(display))
                print()
                
                print("well done,you guessed the word.")


