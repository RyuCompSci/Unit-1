### Blackjack Text-Based Game

```.py
# importing random module
import random
import time

print("\n\n\nWelcome to 'Text-based Blackjack game'")
player_name = str(input("\n\nPlease enter your name: "))

opt = str(input("\n\nWould you like to see the rules of Blackjack? if yes, type 'y'. If no, type 'n'. : "))

if opt == "y":
    print("\n\n\nBlackjack, also known as Twenty-one, is a simple card game. The game requires 52-pack cards and Jokers"
          " are not used for this game. "
          "\n\nOBJECT OF THE GAME"
          "\nThe player attempts to beat the dealer by getting a count as close to 21 as possible, without going"
          " over 21."
          "\n\nCARD VALUES"
          "\nIt is up to the player if an ace is worth 1 or 11. Face cards are 10 and any other card is "
          "its pip value."
          "\n\nTHE DEAL"
          "\nWhen the game begins, the player is given two cards face up to him/her. The dealer gets one card face up "
          "and one card face down."
          "\n\nTHE PLAY"
          "\nThe player can decide whether to 'stand' (not ask for another card) or 'hit' (ask for another "
          "card in an attempt to get closer to a count of 21, or even hit 21 exactly).\n The player can continue this "
          "until deciding to stand on the total (if it is 21 or under), or goes 'bust' (if it is over 21). In the "
          "latter case, the player loses."
          "\n\nTHE DEALER'S PLAY"
          "\nWhen the player's turn is over, the dealers face-down card is turned up. If the total of the cared ranks "
          "is 17 or more, it must stand. If the total is 16 or under, the \ndealer must take a card. The dealer must "
          "continue to take cards until the total is 17 or more, at which point the dealer must stand.The dealer's "
          "decisions are all automatic."
          "\n\nTHE ISSUE"
          "\nWhen the dealer's turn is over, if the dealer's total score is not over 21 and closer to 21 than the "
          "player's, the player loses. Otherwise, the player wins. When the \nplayer's score and the dealer's score is "
          "even, the player loses. Also, when both of them bust or make blackjack, the player loses.")
    input("\n\n\nPress enter to start a game...")

# listing all the suits and ranks of cards
cards_rank = ["A", "2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K"]
cards_suit = ["???", "???", "???", "???"]

# allocating random cards to the player and the dealer
dealer1 = random.choice(cards_rank) + random.choice(cards_suit)
dealer2 = random.choice(cards_rank) + random.choice(cards_suit)
player1 = random.choice(cards_rank) + random.choice(cards_suit)
player2 = random.choice(cards_rank) + random.choice(cards_suit)

# ascii illustration of cards
hiddencard = """
?????????????????????????????????
?????????????????????????????????
?????????????????????????????????
?????????????????????????????????
?????????????????????????????????
?????????????????????????????????
?????????????????????????????????
?????????????????????????????????
?????????????????????????????????
"""
opencard = """
?????????????????????????????????
???{}     {}???
???         ???
???         ???
???    {} {}???
???         ???
???         ???
???     {}{}???
?????????????????????????????????
"""
# Count the time
time_sta = time.time()
# Straightening the line of the right side of ascii card
print(f"\n\n\nYour cards")
time.sleep(1)
if player1[0] == "10" and player2[0] == "10":
    print(opencard.format(player1[0], "  ", player1[1], "   ", "  ", player1[0]),
          opencard.format(player2[0], "  ", player2[1], "   ", "  ", player2[0]))
elif player1[0] == "10" and player2[0] != "10":
    print(opencard.format(player1[0], "  ", player1[1], "   ", "   ", player1[0]),
          opencard.format(player2[0], "   ", player2[1], "   ", "   ", player2[0]))
elif player1[0] != "10" and player2[0] == "10":
    print(opencard.format(player1[0], "   ", player1[1], "   ", "  ", player1[0]),
          opencard.format(player2[0], "  ", player2[1], "   ", "  ", player2[0]))
else:
    print(opencard.format(player1[0], "   ", player1[1], "   ", "   ", player1[0]),
          opencard.format(player2[0], "   ", player2[1], "   ", "   ", player2[0]))

# Straightening the line of the right side of ascii card
time.sleep(2)
print(f"Dealer's cards")
time.sleep(1)
if dealer1[0] == "10":
    print(opencard.format(dealer1[0], "  ", dealer1[1], "   ", "  ", dealer1[0]))
    print(hiddencard)
else:
    print(opencard.format(dealer1[0], "   ", dealer1[1], "   ", "   ", dealer1[0]))
    print(hiddencard)

sum_rank_player = 0
# inputting the ranks of the cards
if player1[0] == "J" or player1[0] == "Q" or player1[0] == "K":
    sum_rank_player += 10
elif player1[0] == "A":
    sum_rank_player += 11
else:
    sum_rank_player += int(player1[0])

if player2[0] == "J" or player2[0] == "Q" or player2[0] == "K":
    sum_rank_player += 10
elif player2[0] == "A" and sum_rank_player == 11:
    sum_rank_player += 1
elif player2[0] == "A" and sum_rank_player <= 10:
    sum_rank_player += 11
else:
    sum_rank_player += int(player2[0])

time.sleep(1.5)
print("\nYour score is ", sum_rank_player)

# player's turn
while sum_rank_player < 21:
    time.sleep(1.5)
    option = input("\n\nIf you want to hit, type 'y'. If you want to stand, type 'n': ")
    if option == "y":
        player_rank = random.choice(cards_rank)
        player_suit = random.choice(cards_suit)
        if player_rank == "J" or player_rank == "Q" or player_rank == "K":
            sum_rank_player += 10
            print(opencard.format(player_rank, "   ", player_suit, "   ", "   ", player_rank))
            time.sleep(1)
            print("\n\nYour score is ", sum_rank_player)
        elif player_rank == "A" and sum_rank_player >= 11:
            sum_rank_player += 1
            print(opencard.format(player_rank, "   ", player_suit, "   ", "   ", player_rank))
            time.sleep(1)
            print("\n\nYour score is ", sum_rank_player)
        elif player_rank == "A" and sum_rank_player < 11:
            sum_rank_player += 11
            print(opencard.format(player_rank, "   ", player_suit, "   ", "   ", player_rank))
            time.sleep(1)
            print("\n\nYour score is ", sum_rank_player)
        elif player_rank == "10":
            sum_rank_player += 10
            print(opencard.format(player_rank, "  ", player_suit, "   ", "  ", player_rank))
            time.sleep(1)
            print("\n\nYour score is ", sum_rank_player)
        else:
            sum_rank_player += int(player_rank)
            print(opencard.format(player_rank, "   ", player_suit, "   ", "   ", player_rank))
            time.sleep(1)
            print("\n\nYour score is ", sum_rank_player)
    else:
        break

time.sleep(1.5)
# Intermediate results
if sum_rank_player > 21:
    print("\nBust")
    time.sleep(1)
    print("\nYou lose")
    time_end = time.time()
    issue = "Lose"
else:
    print("\n\nYour score is ", sum_rank_player)
    time.sleep(1.8)

    print("\n\n\nDealer's turn")
    time.sleep(1.5)

    print("\n\nThe faced-down card is flipped over")
    time.sleep(2)

    if dealer2[0] == "10":
        print(opencard.format(dealer2[0], "  ", dealer2[1], "   ", "  ", dealer2[0]))
    else:
        print(opencard.format(dealer2[0], "   ", dealer2[1], "   ", "   ", dealer2[0]))
    time.sleep(1.5)
    print("The other card is ")

    if dealer1[0] == "10":
        print(opencard.format(dealer1[0], "  ", dealer1[1], "   ", "  ", dealer1[0]))
    else:
        print(opencard.format(dealer1[0], "   ", dealer1[1], "   ", "   ", dealer1[0]))
    sum_rank_dealer = 0

    # inputting the ranks of the cards
    if dealer1[0] == "J" or dealer1[0] == "Q" or dealer1[0] == "K":
        sum_rank_dealer += 10
    elif dealer1[0] == "A":
        sum_rank_dealer += 11
    else:
        sum_rank_dealer += int(dealer1[0])

    if dealer2[0] == "J" or dealer2[0] == "Q" or dealer2[0] == "K":
        sum_rank_dealer += 10
    elif dealer2[0] == "A" and sum_rank_dealer == 11:
        sum_rank_dealer += 1
    elif dealer2[0] == "A" and sum_rank_dealer <= 10:
        sum_rank_dealer += 11
    else:
        sum_rank_dealer += int(dealer2[0])

    print("\nDealer's score is ", sum_rank_dealer)
    time.sleep(1.5)

    while sum_rank_dealer <= 16:
        time.sleep(1.5)
        dealer_rank = random.choice(cards_rank)
        dealer_suit = random.choice(cards_suit)
        if dealer_rank == "J" or dealer_rank == "Q" or dealer_rank == "K":
            sum_rank_dealer += 10
            print(opencard.format(dealer_rank, "   ", dealer_suit, "   ", "   ", dealer_rank))
            time.sleep(1.5)
            print("\nDealer's score is ", sum_rank_dealer)
        elif dealer_rank == "A" and sum_rank_dealer >= 11:
            sum_rank_dealer += 1
            print(opencard.format(dealer_rank, "   ", dealer_suit, "   ", "   ", dealer_rank))
            time.sleep(1.5)
            print("\nDealer's score is ", sum_rank_dealer)
        elif dealer_rank == "A" and sum_rank_dealer < 11:
            sum_rank_dealer += 11
            print(opencard.format(dealer_rank, "   ", dealer_suit, "   ", "   ", dealer_rank))
            time.sleep(1.5)
            print("\nDealer's score is ", sum_rank_dealer)
        elif dealer_rank == "10":
            sum_rank_dealer += 10
            print(opencard.format(dealer_rank, "  ", dealer_suit, "   ", "  ", dealer_rank))
            time.sleep(1.5)
            print("\nDealer's score is ", sum_rank_dealer)
        else:
            sum_rank_dealer += int(dealer_rank)
            print(opencard.format(dealer_rank, "   ", dealer_suit, "   ", "   ", dealer_rank))
            time.sleep(1.5)
            print("\nDealer's score is ", sum_rank_dealer)
    time.sleep(1.5)
    if sum_rank_dealer > 21 and sum_rank_player < 21:
        print("\nYou win")
        time_end = time.time()
        issue = "Win"
    elif 21 >= sum_rank_dealer > sum_rank_player:
        print("\nYou lose")
        time_end = time.time()
        issue = "Lose"
    elif sum_rank_dealer < 21 and sum_rank_dealer < sum_rank_player:
        print("\nYou win")
        time_end = time.time()
        issue = "Win"
    elif sum_rank_dealer == sum_rank_dealer:
        print("\nDraw")
        time_end = time.time()
        issue = "Draw"

time.sleep(2)
print("\n\n" + "Name: ", player_name)
tim = time_end - time_sta
print("Time: ", str(round(tim)) + "s")
print("Score: ", sum_rank_player)


# encode the data of the players into caesar cypher
def caesar_cypher(shift: int, message: str):
    encoded_message = ''
    for i in range(len(message)):
        letter = message[i]
        letter_code = ord(letter)
        # if we "z" and shift=3, 122+3=125 =>'}'
        # but we need 'c' which is 99
        shifted_code = letter_code + shift
        if letter_code + shift > 122:
            # if we go beyond "z" we circle back to "a"
            shifted_code -= 26
        encoded_message += chr(shifted_code)
    return encoded_message


# Uploading the results to a file
with open("database.txt", "a") as files:
    data = f"{player_name}, {sum_rank_player}, {issue}, {round(tim)}\n"
    files.write(data)

```
