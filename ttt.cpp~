# include <iostream>
# include <cstring>
using namespace std;

int board[3][3];
const int BLANK = 0;
const int X_MOVE = 1;
const int O_MOVE = 2;
const int X_TURN = 0;
const int O_TURN = 1;

int turn = X_TURN;

int numXWins = 0;
int numOWins = 0;
int numTies = 0;

void printBoard();
void resetGame();
bool checkWin(int player);
bool checkTie();
bool stillPlaying = true;
char input[2];
int inputLen = 0;
char yon = 'y';

int main() {
  bool stillPlaying = true;
  
  while (stillPlaying == true) {
    printBoard();
    cin >> input;
    inputLen = strlen(input);
      
    while (checkWin(X_MOVE) == false && checkWin(O_MOVE) == false && checkTie() == false) {
    
      if (inputLen != 2) {
	cout << "Enter a letter followed by a number" << endl;
      }
      else if (input[0] != 'a' &&
	       input[0] != 'b' &&
	       input[0] != 'c') {
	cout << "Row must be an a, b, or c" << endl;
      }
      else if (input[1] != '1' &&
	       input[1] != '2' &&
	       input[1] != '3') {
	cout << "Column must be an 1, 2, or 3" << endl;
      }
      else {
	int row = input[0] - 'a';
	int column = input[1] - '1';

	if (board[row][column] == BLANK) {
	  if (turn == X_TURN) {
	    board[row][column] = X_MOVE;
	    turn = O_TURN;	  
	  }
	  else {
	    board[row][column] = O_MOVE;
	    turn = X_TURN;
	  }
	}

	else {
	  cout << "There's a piece there!" << endl;
	}
      }
    }
  

    if (checkWin(X_MOVE) == true) {
      cout << "X Wins!" << endl;
      numXWins++;
    }
    else if (checkWin(O_MOVE) == true) {
      cout << "O Wins!" << endl;
      numOWins++;
    }

    cout << '\n' << "Scoreboard: " << '\n' << "X wins = " << numXWins << " , O wins = " << numOWins << '\n' << endl;

    cout << "Play again? (Y or N?)" << endl;

    cin >> yon;
    if (yon == 'y' || yon == 'Y') {
      resetGame();
      stillPlaying = true;
      continue;

    } else {
      stillPlaying = false;
      return 0;
    }
  }
  return 0;
}

bool checkWin(int player) {
  //row 1
  if (board[0][0] == player && board[0][1] == player && board [0][2] == player) {
    return true;
  }
  //row 2
  if (board[1][0] == player && board[1][1] == player && board [1][2] == player) {
    return true;
  }
  //row 3
  if (board[2][0] == player && board[2][1] == player && board [2][2] == player) {
    return true;
  }
  

  //column 1
  if (board[0][0] == player && board[1][0] == player && board [2][0] == player) {
    return true;
  }
  //column 2
  if (board[0][1] == player && board[1][1] == player && board [2][1] == player) {
    return true;
  }
  //column 3
  if (board[0][2] == player && board[1][2] == player && board [2][2] == player) {
    return true;
  }

  // diagonal top left - bottom right
  if (board[0][0] == player && board[1][1] == player && board [2][2] == player) {
    return true;
  }
  // diagonal bottom left - top right
  if (board[2][0] == player && board[1][1] == player && board [0][2] == player) {
    return true;
  }

  return false;
}

bool checkTie() {
  for (int row = 0; row < 3; row++) {
    for (int column = 0; column < 3; column++) {
      if (board[row][column] == BLANK) {
	return false;
      }
    }
  }
  cout << "It's a tie!" << endl;
  numTies ++;
  return true;
}

 void printBoard() {
  cout << "\t1\t2\t3" << endl;
  for (int row = 0; row < 3; row++) {
    char rowNum = 'a' + row;
    cout << rowNum << '\t'; 
  
    for (int column = 0; column < 3; column++) {
      if (board[row][column] == BLANK) {
	cout << "\t"; 
      }
      else if (board[row][column] == X_MOVE) {
	cout << "X\t";
      }
      else if (board[row][column] == O_MOVE) {
	cout << "O\t";
      }
    }
    cout << ' ' << endl;
  }
 }

void resetGame() {
  //int board = new int[3][3];
  memset(board, 0, sizeof(board));
  turn = X_TURN;
}

   
