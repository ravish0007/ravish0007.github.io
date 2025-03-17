---
title: Validating Sudoku
---

I was asked to validate a sudoku, So far I've never tried it although I have come across this multiple times.
I wrote some code with naive approach, one board state and bunch of impure functions around it.

<!--more-->

```javascript
const board = [];

function init() {
  for (let i = 0; i < 9; i++) {
    board.push([null, null, null, null, null, null, null, null, null]);
  }
}

function validateInputs(row, col, value) {
  if (row > 8 || row < 0) {
    throw new Error("row in not in range");
  }

  if (col > 8 || col < 0) {
    throw new Error("row in not in range");
  }

  if (value > 9 || value < 1) {
    throw new Error("value in not in range");
  }
}

function printBoard() {
  console.log(
    board
      .map((row) => row.map((element) => (element ? element : " ")).join("|"))
      .join("\n")
  );
}

function validateRows() {
  let seen = {};
  for (const row of board) {
    for (const number of row) {
      if (number && number in seen) {
        return false;
      } else {
        seen[number] = true;
      }
    }
    seen = {};
  }
  return true;
}

function validateColumns() {
  let seen = {};
  for (let col = 0; col < 9; col++) {
    for (let row = 0; row < 9; row++) {
      const number = board[row][col];
      if (number && number in seen) {
        return false;
      } else {
        seen[number] = true;
      }
    }
  }
  return true;
}

function validateBoxes() {
  seen = {};
  for (let r = 0; r < 9; r = r + 3) {
    for (let c = 0; c < 9; c = c + 3) {
      for (let row = 0; row < 3; row++) {
        for (let col = 0; col < 3; col++) {
          const number = board[r + row][c + col];
          if (number && number in seen) {
            return false;
          } else {
            seen[number] = true;
          }
        }
      }
    }
  }
  return true;
}

function validateBoardState() {
  isRowValid = validateRows();
  isColumnValid = validateColumns();
  isBoxesValid = validateBoxes();
  return isRowValid && isColumnValid && isBoxesValid;
}

function sudoku([indices, value]) {
  const [row, col] = indices;

  validateInputs(row, col, value);

  if (board[row][col]) {
    throw new Error("positon in the board is already occupied");
  }

  board[row][col] = value;
  const isValid = validateBoardState();
  if (!isValid) {
    board[row][col] = null;
  }
}

init();
sudoku([[0, 0], 2]);
sudoku([[0, 1], 3]);
sudoku([[0, 2], 4]);
sudoku([[1, 0], 5]);
sudoku([[1, 1], 6]);
sudoku([[1, 2], 7]);
sudoku([[2, 0], 8]);
sudoku([[2, 1], 9]);
sudoku([[2, 2], 9]);
// sudoku([[0, 2], 4]);
printBoard();
```
