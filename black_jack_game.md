### Black Jack Text-Based Game

```.py
#importing random module
import random

#listing all the suits and ranks of cards
cards_rank=["A","2","3","4","5","6","7","8","9","10","J","Q","K"]
cards_suit=["♠","♥","♣","♦"]
dealer1=random.choice(cards_rank)+random.choice(cards_suit)
dealer2=random.choice(cards_rank)+random.choice(cards_suit)
player1=random.choice(cards_rank)+random.choice(cards_suit)
player2=random.choice(cards_rank)+random.choice(cards_suit)
hiddencard="""
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
opencard="""
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

print(f"Your cards")
if player1[0]=="10" and player2[0]=="10":
    print(opencard.format(player1[0],"  ",player1[1],"   ","  ",player1[0]),opencard.format(player2[0],"  ",player2[1],"   ","  ",player2[0]))
elif player1[0]=="10" and player2[0]!="10":
    print(opencard.format(player1[0], "  ", player1[1], "   ", "   ",player1[0]),opencard.format(player2[0], "   ", player2[1], "   ", "   ", player2[0]))
elif player1[0]!="10" and player2[0]=="10":
    print(opencard.format(player1[0], "   ", player1[1], "   ", "  ",player1[0]),opencard.format(player2[0], "  ", player2[1], "   ", "  ", player2[0]))
else:
    print(opencard.format(player1[0], "   ", player1[1], "   ", "   ",player1[0]),opencard.format(player2[0], "   ", player2[1], "   ", "   ", player2[0]))

print(f"Dealer's cards")
dealer_rank1=player1[0]
dealer_suit1=player1[1]
if dealer1[0]=="10":
    print(opencard.format(dealer1[0],"  ",dealer1[1],"   ","  ",dealer1[0]))
    print(hiddencard)
else:
    print(opencard.format(dealer1[0], "   ", dealer1[1], "   ", "   ", dealer1[0]))
    print(hiddencard)

if player1[0] == "J" or "Q" or "K":
    sum_rank_player = 10
elif player1[0] == "A":
    sum_rank_player = 11
else:
    sum_rank_player = int(player1[0])
if player2[0] == "J" or "Q" or "K":
    sum_rank_player += 10
elif player2[0] == "A":
    sum_rank_player += 11
else:
    sum_rank_player += int(player2[0])
while sum_rank_player<=21:
    option = input("If you want to hit, type 'y'. If you want to stand, type 'n'")
    if option=="n":
        print("Your score is ",sum_rank_player)
        break
    elif option=="y":
        player_rank=random.choice(cards_rank)
        player_suit=random.choice(cards_suit)
        if player_rank=="J" or "Q" or "K":
            sum_rank_player+=10
        elif player_rank=="A":
            sum_rank_player+=11
        else:
            sum_rank_player+=int(player_rank)
        if player_rank=="10":
            print(opencard.format(player_rank, "  ", player_suit, "   ", "  ", player_rank, "  "))

        else:
            print(opencard.format(player_rank, "   ", player_suit, "   ", "   ", player_rank))
```
