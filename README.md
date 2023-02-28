# Checkers 

Checker (or Draughts) is a worldwide two players board game. The game is typically played on the same board as chess and the objective is to capture all of the opponent's pieces by jumping over them with one's own pieces. Each player starts with 12 pawns that can only move forward and diagonally on the black squares of the board. When a pawn reaches the last row of the board, it is promoted to a Queen (or King), a more powerful piece that can also move backwards.

<p align="center">
  <img src="https://user-images.githubusercontent.com/35597877/137335322-f02f5183-8892-4cd3-837d-de44bc853828.png" width="150">
</p>


# Checkers and AI
Checkers, unlike chess, has regional variations around the world. The English variant is the most prevalent in the US and UK, while the International variant is popular in Northern Europe and the Italian variant is played in Italy and Northern Africa. Due to the variety of different versions of checkers, there are not necessarily AI systems that can play all of these variants. In fact, the English variant has received the most attention, and surprisingly, it is difficult to find a computer program that can play well in some variants of checkers.

## Chinook - English variant
In 1994, Chinook, a computer program, achieved a historic milestone by becoming the first AI system to win a world champion title in a Checkers competition against humans. This achievement has led to the English variant becoming the most popular in research involving computer science and Checkers. The English variant was weakly solved in 2007 and remains the most complex game ever solved to this day.

## Italian Variant
The Italian checkers (Dama Italiana) variant is very similar to the English one, with the main differences lying in the eating priorities. Specifically, in the Italian version, pawns **cannot** eat queens, whereas in the English variant, they can. In other words, queens can only be taken by other queens, making them a more crucial and powerful piece. For more information on the origin and rules of the game, please visit the following [page](https://en.wikipedia.org/wiki/Italian_draughts).
While browsing online, we were unable to find an AI that could play Italian Dama at a sufficiently high level. We were also unable to find a computer program that could beat us. As a result, we decided to build the first AI capable of challenging the World Champion of Italian Dama.

# Eldo
Eldo is the first known AI system trained with Deep Reinforcement Learning to play Italian Checkers at a superhuman level. The system was trained using a Deep Q-Learning algorithm, which differs from previous heuristic algorithms. Reinforcement Learning is a Machine Learning area where the AI learns by interacting with the environment. In Eldo's case, it learned the game by playing it, similar to how a child learns to play. Eldo had no prior information about the game environment, rules, or objective. Its only input was the 8x8 board setup, where it determined for each of the 64 squares whether they were free or occupied by a black or white piece.

# Deep Q-Learning
Deep Q-Learning is a type of Reinforcement Learning algorithm that uses a deep neural network to approximate the action-value function of a given state-action pair in a reinforcement learning problem. In simpler terms, the algorithm learns to make optimal decisions by taking actions that maximize the expected future reward. The "Q" in Q-Learning refers to the function that calculates the expected reward for each action in a given state. Deep Q-Learning uses a deep neural network to approximate this function, allowing the algorithm to learn more complex decision-making strategies in high-dimensional state spaces. The algorithm involves the use of an experience replay buffer to store past experiences, a target network to stabilize learning, and an epsilon-greedy policy to balance exploration and exploitation. Deep Q-Learning has been successfully applied to a variety of applications, including playing games at superhuman levels, robotic control, and autonomous driving.

