### Black Jack Text-Based Game

```.py
# importing random module
import random
import time

# listing all the suits and ranks of cards
cards_rank = ["A", "2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K"]
cards_suit = ["♠", "♥", "♣", "♦"]

# allocating random cards to the player and the dealer
dealer1 = random.choice(cards_rank)+random.choice(cards_suit)
dealer2 = random.choice(cards_rank)+random.choice(cards_suit)
player1 = random.choice(cards_rank)+random.choice(cards_suit)
player2 = random.choice(cards_rank)+random.choice(cards_suit)

# ascii illustration of cards
hiddencard = """
┌─────────┐
│░░░░░░░░░│
│░░░░░░░░░│
│░░░░░░░░░│
│░░░░░░░░░│
│░░░░░░░░░│
│░░░░░░░░░│
│░░░░░░░░░│
└─────────┘
"""
opencard = """
┌─────────┐
│{}     {}│
│         │
│         │
│    {} {}│
│         │
│         │
│     {}{}│
└─────────┘
"""
# Straightening the line of the right side of ascii card
print(f"\n\n\nYour cards")
time.sleep(1)
if player1[0] == "10" and player2[0] == "10":
    print(opencard.format(player1[0], "  ", player1[1], "   ", "  ", player1[0]), opencard.format(player2[0], "  ", player2[1], "   ", "  ", player2[0]))
elif player1[0] == "10" and player2[0] != "10":
    print(opencard.format(player1[0], "  ", player1[1], "   ", "   ",player1[0]),opencard.format(player2[0], "   ", player2[1], "   ", "   ", player2[0]))
elif player1[0] != "10" and player2[0] == "10":
    print(opencard.format(player1[0], "   ", player1[1], "   ", "  ", player1[0]), opencard.format(player2[0], "  ", player2[1], "   ", "  ", player2[0]))
else:
    print(opencard.format(player1[0], "   ", player1[1], "   ", "   ",player1[0]),opencard.format(player2[0], "   ", player2[1], "   ", "   ", player2[0]))

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
if sum_rank_player == 21:
    print("\n\nYou win")
else:
    print("\n\nYour score is ", sum_rank_player)
    time.sleep(1.8)

    print("\n\n\nDealer's turn")
    time.sleep(1.5)

    print("\n\nThe hidden card is flipped over")
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
            time.sleep(1)
            print("\nDealer's score is ", sum_rank_dealer)
        elif dealer_rank == "A" and sum_rank_dealer >= 11:
            sum_rank_dealer += 1
            print(opencard.format(dealer_rank, "   ", dealer_suit, "   ", "   ", dealer_rank))
            time.sleep(1)
            print("\nDealer's score is ", sum_rank_dealer)
        elif dealer_rank == "A" and sum_rank_dealer < 11:
            sum_rank_dealer += 11
            print(opencard.format(dealer_rank, "   ", dealer_suit, "   ", "   ", dealer_rank))
            time.sleep(1)
            print("\nDealer's score is ", sum_rank_dealer)
        elif dealer_rank == "10":
            sum_rank_dealer += 10
            print(opencard.format(dealer_rank, "  ", dealer_suit, "   ", "  ", dealer_rank))
            time.sleep(1)
            print("\nDealer's score is ", sum_rank_dealer)
        else:
            sum_rank_dealer += int(dealer_rank)
            print(opencard.format(dealer_rank, "   ", dealer_suit, "   ", "   ", dealer_rank))
            time.sleep(1)
            print("\nDealer's score is ", sum_rank_dealer)
    time.sleep(1.5)
    if sum_rank_dealer > 21 and sum_rank_player > 21:
        print("\nYou lose")
    elif sum_rank_dealer > 21 and sum_rank_player < 21:
        print("\nYou win")
    elif 21 >= sum_rank_dealer > sum_rank_player:
        print("\nYou lose")
    elif sum_rank_dealer < 21 and sum_rank_dealer < sum_rank_player:
        print("\nYou win")
    elif sum_rank_dealer == sum_rank_dealer:
        print("\nDraw")
```
