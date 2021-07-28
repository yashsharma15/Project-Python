import random

def pick_random_word():
    word_list = ['flower','board','aeroplane','rats','mouse']
    selected_index = random.randint(0,len(word_list)-1)
    return word_list[selected_index]

def change_current_word_state(selected_word,current_word_state,character):
    modified_word_state = ""

    for i in range(len(selected_word)):
        if current_word_state[i] == "_" and selected_word[i] == character:
            modified_word_state+=character
        else:
            modified_word_state+=current_word_state[i]

    return modified_word_state

def input_character_in_word(selected_word,input_char,current_word_state,attempts_remaining):
    if input_char in selected_word:
        current_word_state = change_current_word_state(selected_word,current_word_state,input_char)
    else:
        attempts_remaining-=1
    return current_word_state,attempts_remaining

def print_current_state(current_word_state,attempts_remaining):
    print("current state:",end=" ")
    
    for i in current_word_state:
        print(i,end=" ")

    print("\tattempts_remaining: {}".format(attempts_remaining))

def check_game_status(selected_word,current_word_state,attempts_remaining):
    if current_word_state == selected_word:
        print("Congrats! you won the game:D")
        return True

    if attempts_remaining <=0:
        print("Sorry! you lost! :(please try again")
        print("word was : {}".format(selected_word))
        return True

    return False

def play_game(attempts=5):
    selected_word = pick_random_word()
    current_word_state = "_" * len(selected_word)
    attempts_remaining = attempts
    print_current_state(current_word_state,attempts)
    while True:
        input_char = input("Guess the character:")
        print("")
        current_word_state,attempts_remaining = input_character_in_word(selected_word,input_char,current_word_state,attempts_remaining)
        print_current_state(current_word_state,attempts_remaining)
        game_ended = check_game_status(selected_word,current_word_state,attempts_remaining)
        if game_ended:
            break
        
play_game()
