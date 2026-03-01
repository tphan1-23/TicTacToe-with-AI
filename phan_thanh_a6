import random

def drawBoard(board):
    print(board[7] + '|'+board[8] + '|'+board[9])
    print('-+-+-')
    print(board[4] + '|'+board[5] + '|'+board[6])
    print('-+-+-')
    print(board[1] + '|'+board[2] + '|'+board[3])

def inputPlayerLetter():
    letter = ''
    while not (letter == 'X' or letter == 'O'):
        print('Which one do you want to be? (X or O)')
        letter = input().upper()
    if letter == 'X':
        return ['X', 'O']
    else:
        return ['O', 'X']
    
def whoGoesFirst():
    if random.randint(0, 1) == 0:
        return 'computer'
    else:
        return 'player'
    
def makeMove(board, letter, move):
    board[move] = letter

def isWinner(bo, le):
    return ((bo[7] == le and bo[8] == le and bo[9] == le) or
            (bo[4] == le and bo[5] == le and bo[6] == le) or
            (bo[1] == le and bo[2] == le and bo[3] == le) or
            (bo[7] == le and bo[4] == le and bo[1] == le) or
            (bo[8] == le and bo[5] == le and bo[2] == le) or
            (bo[9] == le and bo[6] == le and bo[3] == le) or
            (bo[7] == le and bo[5] == le and bo[3] == le) or
            (bo[9] == le and bo[5] == le and bo[1] == le))

def isSpaceFree(board, move):
    return board[move] == ' '
def getPlayerMove(board):
    move = ' '
    while move not in '1 2 3 4 5 6 7 8 9'.split() or not isSpaceFree(board, int(move)):
        print('What is your next move? Choose from 1 to 9')
        move = input()
    return int(move)
def isBoardFull(board):
    for i in range(1, 10):
        if isSpaceFree(board, i):
            return False
    return True

def minimax(board, isMaximizing, computerLetter, playerLetter):
    if isWinner(board, computerLetter):
        return 10
    elif isWinner(board, playerLetter):
        return -10
    elif isBoardFull(board):
        return 0

    if isMaximizing:
        bestScore = -float('inf')
        for i in range(1, 10):
            if isSpaceFree(board, i):
                board[i] = computerLetter
                score = minimax(board, False, computerLetter, playerLetter)
                board[i] = ' '
                bestScore = max(score, bestScore)
        return bestScore
    else:
        bestScore = float('inf')
        for i in range(1, 10):
            if isSpaceFree(board, i):
                board[i] = playerLetter
                score = minimax(board, True, computerLetter, playerLetter)
                board[i] = ' '
                bestScore = min(score, bestScore)
        return bestScore
    
def getComputerMove(board, computerLetter):
    if computerLetter == 'X':
        playerLetter ='O'
    else:
        playerLetter = 'X'

    bestScore = -float('inf')
    bestMove = -1

    for i in range(1,10):
        if isSpaceFree(board, i):
            board[i] = computerLetter
            score = minimax(board, False, computerLetter, playerLetter)
            board[i] = ' '
            if score > bestScore:
                bestScore = score
                bestMove = i
    return bestMove

print('Are you ready to play some Tic Tac Toe~?')

while True:
    theBoard = [' '] * 10
    playerLetter, computerLetter = inputPlayerLetter()
    turn = whoGoesFirst()
    print('The ' + turn + ' will go first')
    gameIsPlaying = True

    while gameIsPlaying:
        if turn == 'player':
            drawBoard(theBoard)
            move = getPlayerMove(theBoard)
            makeMove(theBoard, playerLetter, move)

            if isWinner(theBoard, playerLetter):
                drawBoard(theBoard)
                print('You have won!')
                gameIsPlaying = False
            else:
                if isBoardFull(theBoard):
                    drawBoard(theBoard)
                    print('It a tie!')
                    break
                else:
                    turn = 'computer'
        else:
            move = getComputerMove(theBoard, computerLetter)
            makeMove(theBoard, computerLetter, move)

            if isWinner(theBoard, computerLetter):
                drawBoard(theBoard)
                print('Sadly You lose')
                gameIsPlaying = False
            else:
                if isBoardFull(theBoard):
                    drawBoard(theBoard)
                    print('It a tie!')
                    break
                else:
                    turn = 'player'

        

      