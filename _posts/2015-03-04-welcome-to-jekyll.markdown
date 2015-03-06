---
layout: post
title:  "Python: BattleShip"
date:   2015-03-04 11:48:34
categories: jekyll update
---
This is one of my first python based projects. I made this battle ship game following the tutorial on [Codecademy][codecademy.com] check out the source code below!

{% highlight ruby %}
from random import randint

board = []

for x in range(5):
    board.append(["O"] * 5)

def print_board(board):
    for row in board:
        print " ".join(row)

print "Let's play Battleship!"
print_board(board)

def random_row(board):
    return randint(0, len(board) - 1)

def random_col(board):
    return randint(0, len(board[0]) - 1)
x
ship_row = random_row(board)
ship_col = random_col(board)

for turn in range(4):
    guess_row = int(raw_input("Guess Row:")) - 1
    guess_col = int(raw_input("Guess Col:")) - 1
    board[guess_row][guess_col] = "X"
    print "You missed the ship! Guess again."
    print_board(board)



    if guess_row == ship_row and guess_col == ship_col:
        print "Congratulations! You sunk my battleship!"
        break
else:
    if (guess_row < 0 or guess_row > 4) or (guess_col < 0 or guess_col > 4):
        print "Oops, that's not even in the ocean."
    elif(board[guess_row][guess_col] == "X"):
            print "You guessed that one already."
    else:
        print "You missed my battleship!"
        board[guess_row][guess_col] = "X"
    if turn == 3:
        print "Game Over"
        print "Turn", turn + 1
        print_board(board)

print "The Ship was located at %s, %s" % (ship_row, ship_col)





{% endhighlight %}



[codecademy.com]: http://www.codecademy.com/
[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
