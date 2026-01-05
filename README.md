# Tic-Tac-Toe 

## Overview

This project demonstrates how to implement a **Q-learning** agent that learns to play **Tic-Tac-Toe**. 
The agent uses reinforcement learning to improve its performance by playing many games and adjusting its strategy over time.

The Q-learning algorithm is a type of **model-free** reinforcement learning where the agent learns the optimal policy by updating its Q-values (state-action values) based on rewards it receives after performing actions.

---

## Contents
1. [How the Code Works](#how-the-code-works)
2. [Usage](#usage)
3. [Key Concepts in Q-Learning](#key-concepts-in-q-learning)
4. [License](#license)

---

## How the Code Works
### 1. Tic-Tac-Toe Environment
   The TicTacToe class simulates a 3x3 Tic-Tac-Toe game. It handles the following functions:
   - Game Initialization: Initializes the board and sets up players ("X" and "O").
   - Available Moves: Returns a list of available moves (empty spaces on the board).
   - Make Move: Updates the board with the player’s move and checks for a winner.
   - Switch Player: Alternates between players after each move.
   - Check Winner: Checks if a player has won the game (either by row, column, or diagonal).
   - Print Board: Prints the current state of the board for visualization.

### 2. QLearningAgent
   The QLearningAgent class defines the agent that uses Q-learning to decide its actions based on its experiences during the game:
   - get_Q_value: Retrieves the Q-value for a given state-action pair.
   - choose_action: Chooses an action based on the epsilon-greedy strategy:
     - With probability epsilon, the agent explores a random move (exploration).
     - Otherwise, the agent exploits the best-known action based on Q-values (exploitation).
   - update_Q_value: Updates the Q-value for the state-action pair using the Bellman Equation.

### 3. Training the Agent
   The train function trains the agent by playing multiple games of Tic-Tac-Toe. The agent learns by interacting with the game environment and updating its Q-values based on the rewards it gets after each move. The process includes:
   - Playing games against a random opponent.
   - Adjusting its Q-values using the rewards (win/loss/tie).
   - Improving its strategy over many episodes.

### 4. Testing the Agent
   After training, the test function evaluates the performance of the trained agent:
   - The agent plays several games against a random opponent.
   - The function calculates the agent’s win percentage based on its performance.

---

## Usage

### 1. Training the Agent
You can train the agent by calling the `train` function. This will play a large number of games (e.g., 100,000) and learn the best moves over time.

### 2. Testing the Agent
Once the agent is trained, you can `test` its performance by calling the test function. The agent will play a number of games (e.g., 1,000) against a random opponent, and you can calculate the win percentage.

### 3. Playing the Game Manually
You can also play Tic-Tac-Toe manually using the game interface. The game will prompt you to enter your moves

---

## Key Concepts in Q-Learning
### Exploration vs Exploitation
- Exploration: The agent sometimes chooses random actions (epsilon-greedy) to explore different moves.
- Exploitation: The agent uses the knowledge it has learned (i.e., the Q-values) to make the best possible move.

### Q-value (State-Action Value)
The Q-value represents the expected future reward of taking a particular action in a specific state. The agent updates these Q-values to learn the best strategies over time.

### Bellman Equation
The Bellman Equation is the key formula used by the Q-learning agent to update its Q-values. It combines the immediate reward and the estimated future reward to compute the new Q-value for a state-action pair.

```python
self.Q[(state_key, action)] = old_Q + self.alpha * (reward + self.gamma * max_next_Q - old_Q)
```

### Training and Testing
- Training: The agent learns by interacting with the environment (playing games).
- Testing: The agent’s performance is evaluated by having it play against a random opponent and calculating its win percentage.

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
