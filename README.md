# Pytorch_snake
A PyTorch based reinforcement learning agent to play snake
 
 ## Analysis Motivation
When I was young, I played the game Snake a lot on my mom's not-so-smart motorola phone. It was a "toxic" game as I could never get a really high score. Fast forward to now, 
I learned about reinforcement learning in my Grad School robotics class and I wanted to see if I could write a simple snake game first and then use PyTorch to train a neural network
to play the game with reinforcement learning. 

## Techniques and Steps to Run
The snake game was created with PyGame.  

For the reinforcement learning part, the important components are specified below:
- Algorithm: Q-learning
- Environment: the snake game itself
- Reward:
  - Eat food: +10
  - Game over: -10
  - Other: 0
- State
  - A boolean list of 11 states
  - [danger straight, danger right, danger left, direction left, direction right, direction up, direction down, food left, food right, food up, food down]
- Action
  - Go straight ([1, 0, 0])
  - Turn right ([0, 1, 0])
  - Turn left ([0, 0, 1])

I designed a feed forward neural network. The structure is as follows:
- Input layer (# of neurons  = 11 / # of states)
- Hidden layer (256 neurons, relu activation)
- Output layer (3 neurons / 3 actions)
- Loss: Mean squared error loss
- Optimizer: Adam


## File Structure
- Python files
  - game.py: the snake game
  - model.py: Feed forward PyTorch model as well as the Q-learning algorithm
  - helper.py: plot the current score and average score as a function of games played
  - agent.py: the main execution file to train and display results

- Other files
  - arial.ttf: file needed to create the snake game in PyGame

## Result
The training agent started playing the game with an exploratory approach, and then as it gets to know the game and possible mooves, the scoring peformance started to improve. The plot
below shows the training result after 120 games.
![Image of result](https://github.com/EngineeringIV/Pytorch_snake/blob/main/Result.PNG)

## Credit and Acknowledgement
This project follows the wonderful [tutorial](https://www.youtube.com/watch?v=PJl4iabBEz0) by [Patrick Leober](https://www.youtube.com/channel/UCbXgNpp0jedKWcQiULLbDTA). 
It also got inspirations from this [tutorial](https://towardsdatascience.com/how-to-teach-an-ai-to-play-games-deep-reinforcement-learning-28f9b920440a) on teaching AI to play games



