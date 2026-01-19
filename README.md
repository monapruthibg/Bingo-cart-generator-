# Bingo-cart-generator-
import random

def generate_bingo_card():
    # Create a list of numbers from 1 to 75
    numbers = list(range(1, 76))
    
    # Randomly select 24 numbers (center is FREE)
    selected_numbers = random.sample(numbers, 24)
    
    # Create empty 5x5 bingo card
    bingo_card = [['' for _ in range(5)] for _ in range(5)]
    
    index = 0
    for i in range(5):
        for j in range(5):
            if i == 2 and j == 2:
                bingo_card[i][j] = "FREE"
            else:
                bingo_card[i][j] = selected_numbers[index]
                index += 1
    
    return bingo_card


def print_bingo_card(card):
    print(" B   I   N   G   O")
    print("-" * 25)
    for row in card:
        for item in row:
            print(f"{str(item):>4}", end=" ")
        print()


# Main program
bingo = generate_bingo_card()
print_bingo_card(bingo)
