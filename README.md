print("welcome to tic tac toe")
player1=input("player1 enter ur name")
player2=input("player2 enter ur name")
board = ["-","-","-","-","-","-","-","-","-"]
game_on=True
current_player="X"
player=player1
def display_board():
    print(board[0]+"|"+board[1]+"|"+board[2])
    print(board[3]+"|"+board[4]+"|"+board[5])
    print(board[6]+"|"+board[7]+"|"+board[8])
def play_game():
    global game_on
    display_board()
    while game_on:
        if (player == 1):
            break
        game_play()
        flip_player()
        check_winner()








def game_play():
        global player1,player2,player
        print(player,end="")
        x=int(input("  choose a number from 1-9"))
        global current_player
        if(board[x-1]=="X"or board[x-1]=="O"):
            print("u cannot enter this position again")
            x =int(input("choose a number from 1-9"))
        while (x > 9 or x == "-"):
            print("invalid number")
            x = int(input("choose the numbers from 1-9"))

        if(x!=None):
            board[x-1]=current_player
            print(display_board())
        return x

def flip_player():
    global current_player,player1,player2,player
    if current_player=="X" and player!=1:
        current_player="O"
        player=player2


    elif current_player=="O" and player!=1:
        current_player="X"
        player=player1

def check_winner():
    check_rows()
    check_column()
    check_diagnols()







def check_rows():
    global player
    if board[0]==board[1]==board[2]=="X" or board[3]==board[4]==board[5]=="X" or board[6]==board[7]==board[8]=="X":
        print(player,"is the winner")
        player=1
    elif board[0]==board[1]==board[2]=="O" or board[3]==board[4]==board[5]=="O" or board[6]==board[7]==board[8]=="0":
        print(player," is winner")
        player=1





def check_column():
    global player
    if board[0]==board[3]== board[6] =="X" or board[1]==board[4]== board[7]=="X" or board[2]==board[5]==board[8]=="X":
        print("player is winner")
        player=1

    elif board[0]==board[3]==board[6]=="O" or board[1]==board[4]== board[7]=="O" or board[2]==board[5]==board[8]=="O":
        print("player is winner")
        player=1

def check_diagnols():
    global player
    if board[0]==board[4]==board[8]=="X" or board[2]==board[4]==board[6]=="X":
        print("player is winner")
        player=1

    elif board[0] == board[4] == board[8] == "O" or board[2] == board[4] == board[6] == "O":
        print("player is winner")
        player=1



play_game()
