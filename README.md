# ML-Enhanced Tic-tac-toe Game

A Python implementation of Tic-tac-toe featuring an AI opponent powered by machine learning. This version combines object-oriented programming with a Random Forest Classifier to create an intelligent opponent.

## Features

### AI Implementation
- Uses Random Forest Classifier for move prediction
- Combines ML predictions with strategic position values
- Fallback strategy for early game and unknown positions
- Hybrid decision-making system for optimal moves

### Game Components
- Object-oriented design with separate Board and Game classes
- Human vs AI gameplay
- Input validation and error handling
- Win/draw detection
- Multiple game sessions

## Technical Requirements

### Dependencies
```python
import numpy as np
import pandas as pd
from sklearn.ensemble import RandomForestClassifier
import random
```

### Data Requirements
- Requires 'tictac_final.txt' dataset for ML model training
- Dataset format: x0 x1 x2 x3 x4 x5 x6 x7 x8 y
  - x0-x8: board positions (1 for X, -1 for O, 0 for empty)
  - y: game outcome

## Class Structure

### Board Class
```python
class Board:
    def __init__()           # Initialize empty board
    def printBoard()         # Display current board state
    def updateBoard()        # Update cell with player symbol
    def getCell()           # Get content of specific cell
    def convert_to_ml_state() # Convert board to ML format
```

### MLGame Class
```python
class MLGame:
    def __init__()          # Initialize game and train ML model
    def train_model()       # Train Random Forest model
    def get_ml_move()       # Get AI move using ML
    def playGame()          # Main game loop
    # ... additional game management methods
```

## AI Strategy

### Move Selection Process
1. Convert current board state to ML format
2. Generate and evaluate possible moves
3. Combine ML predictions with position values:
   - Center: 4 points
   - Corners: 3 points
   - Sides: 2 points
4. Select move with highest combined score

### Fallback Strategy
If ML prediction fails:
1. Identify empty positions
2. Rank positions by strategic value
3. Select highest-valued available position

## How to Play

1. Run the program
2. Human plays as X, AI as O
3. Enter moves as "row,column" (e.g., "1,1" for center)
4. Valid input range: 0-2 for both row and column
5. Game continues until win or draw
6. Choose to play another game or exit

## Board Layout
```
R\C |  0  |  1  |  2  | 
-----------------------
 0  |     |     |     | 
-----------------------
 1  |     |     |     | 
-----------------------
 2  |     |     |     | 
-----------------------
```

## Error Handling
- Validates input format and range
- Checks for occupied positions
- Handles invalid inputs gracefully
- Provides clear error messages

## Implementation Notes

### ML Model Training
- Trains new model for each game session
- Uses 100 decision trees in Random Forest
- Converts game states to compatible format

### Position Evaluation
- Strategic position values influence move selection
- Combines ML predictions with positional strategy
- Balances exploration and exploitation

## Future Improvements
- Model persistence between games
- Difficulty levels
- Learning from played games
- Enhanced prediction accuracy
- Performance analytics

## Author
Kuan Chen Chen

## Date
October 27, 2024

## Version
3.0 (ML Enhanced)
