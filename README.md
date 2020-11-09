# first-text-game
first ever text game 
import time
import random


def print_pause(message_to_print):
    print(message_to_print)
    time.sleep(2)


def Intro():
    print_pause("You are waking up in the most dangerous city in America!")
    print_pause("Don't panic just yet, Your a warrior! Pick your head up "
                "and think what should you do next...")


def village_mob():
    print_pause("People from the village notice an outsider"
                "and start to whistle"
                "as they approached.")
    print_pause("To your suprise! Young teens are approaching"
                "looking strangely.")
    print_pause("Then adults holding weapons start approaching taking"
                "a defensive stand towards you.")
    print_pause("As you try to speak, one attacks and you strike him down!")


def new_land():
    print_pause("Looking at the village from afar. "
                " You notice something strange.")
    print_pause("Random weaponed villagers attacking men in need. You dash "
                "deeper into the woods and never looked back!")
    print_pause("Beep-Beep...")


def bad_land():
    print_pause("Looking at the derangged village from a distance "
                "you notice strange activity.")
    print_pause("Rather than see what its about you bolt "
                "into the wilderness..")
    print_pause("You find a beach but its hard to build a foundation on sand.")
    print_pause("You learn to swim and become a mermaid!!")


'''
see start_game text
presented with go to village or recon village
if go to village they will encounter angry mob or wild wildebeast
    user get choice to fight or run
    user lose

if choose recon they can build own colony or turn into mermaid
'''


def start_game():

    print_pause("What would you like to do? "
                "(Please enter 1 or 2.)")

    progress = input("1.Enter 1 to run down the hill to the nearby villiage.\n"
                     "2. Enter 2 to stay in the field and scope out "
                     "the villlage perameter first\n")

    if progress == '1':
        print_pause("You pick your head up, take a deep breath, "
                    "Then you sprint through the field toward the villiage!")
        village_encounter = random.choice(["village_mob", "wilderbeast"])
        if village_encounter == "village_mob":
            angry_mob()
        elif village_encounter == "wilderbeast":
            Wilder_beast()
    elif progress == '2':
        second_choice()
    else:
        print_pause("That is not a valid input. Please pick again.")
        start_game()
        play_again()


def angry_mob():
    print_pause("You have arrived to the villiage.")
    print_pause("You have been greeted by an angry Mob. what you like "
                "to do next??")

    mobchoice = input("1. fight \n"
                      "2. Escape\n")

    if mobchoice == '1':
        print_pause("Villagers attack you with many weapons and you "
                    "are captured for life!! GAME OVER!!")

    elif mobchoice == '2':
        print_pause("Villagers capture you. You still Lose")
    else:
        print_pause("Invalid input. please pick again")


def Wilder_beast():
    print_pause("You arrive looking for help from nearby teens playing by.")
    print_pause("Only to be met unexpectantly by a creature.")
    print_pause("Grrr. A big angry wilderbeast come and attack you with "
                "angry villager standing by.")
    print_pause("NOW YOUR BEING ATTACKED..")
    beastchoice = input("1. fight \n"
                        "2. Escape\n")

    if beastchoice == '1':
        print_pause("Beast becomes super aggressive and attack! GAME OVER!!")

    elif beastchoice == '2':
        print_pause("Wilderbeast chased and eat you... You still Lose")
    else:
        print_pause("Invalid input. please pick again")


def second_choice():
    print_pause("Great choice, You chose to to go to the woodline for "
                "a better view of the strange looking viliage!")
    print_pause("Now that you have cover and a better view of the village "
                "What would you like to do next?")
    print_pause("Enter 1 to continue to recon. Enter 2 to run off!")
    next_progress = input("1. Recon Villiage\n"
                          "2.Go off in the woods and start your own colony!\n")
    if next_progress == '1':
        new_land()
        print_pause("You realize the people in the village are the evil "
                    "people of the land.You go out in the wilderness "
                    "to start building your own villiage "
                    "You find a partner who you live happily ever "
                    "after with. GAME END.. YOU WIN!!!!!")

    elif next_progress == '2':
        bad_land()
        play_again()
    else:
        print_pause("That is not a valid input. Please pick again.")
        second_choice()


def play_again():
    print_pause("Would you like to play again?")
    answer = input("Please write 'Yes' or 'No' ")

    if answer == 'yes':
        print_pause("Ok, playing again..")
        play_game()
    else:
        print_pause("Thanks for playing.")


def play_game():
    Intro()
    start_game()
    play_again()


play_game()
