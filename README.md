# Checkers 

Checker (or Draughts) is a worldwide two players board game. Usually played on the same board as chess, the objective of each player is to capture, i.e. eat, all opponent's pieces. Initially, each player has 12 pawns that can only move forward and diagonally - the game is played only on one colour of the board, typically on the black squares - and can eat by jumping over the opponent's piece. Once a pawn reaches the last row of the board this is promoted into a Queen (or King), a more powerful piece that can also move backwards. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/35597877/137335322-f02f5183-8892-4cd3-837d-de44bc853828.png" width="150">
</p>


# Checkers and AI
Unlike chess, checker is played differently around the world depending on each region. In the US and UK the prevalent version is the English variant. Other popular variants are the International, played mostly in Northern Europe, and the Italian variant played in Italy and Northern Africa. Given the variety of different versions in checkers, there aren't necessarily AI systems that can play each of these variants. As a matter of fact, the English version is the one that has received most attentions and surprinsignly for some checker's variants it is seemingly hard to find a computer program that is able to play well. 

## Chinook - English variant
In 1994, a computer program named Chinook was the first ever artificial system able to win a world champion title in a competition against humans. The AI played the English Checker variant and ever since this version has become the most trending in the research involving computer science and checkers. In 2007, English Checkers was weakly solved and to this day it remains the most complex game ever solved. 

## Italian Variant
The Italian checkers (Dama Italiana) variant is very similar to the English one, with the main differences laying in the eating priorities. Specifically, in the Italian version pawns **cannot** eat queens (in the English variant this is possible). In other words, queens can only be eaten by others queens, making them an even more crucial and powerful piece. For more info concerning the origin and the rule of the game check the following [page](https://en.wikipedia.org/wiki/Italian_draughts).
While browsing online, we were not able find an AI that could play at a sufficiently high level, we did not even find a computer program able to beat us. We thus decided to build the first AI that will be challenge the World CHampion of Italian Dama

# Luigi
Luigi is a Deep Reinforcement Learning system able to play Italian Checkers at super human level. Luigi was trained using a Deep Q-Learning algorithm. Unlike previous heuristic algorithm Reinforcement Learning is an area of Machine Learning where the AI learns only with the interaction of the environment. Instead of feeding our algorithm tons of data of Checkers' games, Luigi was able to learn only by playing the game - basically in a similar way to how you would teach a kid how to play. Luigi had no information of the environment (rules of the games, objective etc..), the only input it received was the set up of the 8x8 board, i.e. for each of the 64 squares whether they are free or occupied by a black or white piece. The AI learned to play against itself using a Q-table, a dataframe where each row represents a state (board set up) and each column represents a possible move. The entries of the table are the associated Q-value.

<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky"><span style="font-weight:bold">Q-Table</span></th>
    <th class="tg-0pky">a1</th>
    <th class="tg-0pky">a2</th>
    <th class="tg-0pky">a3</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">s1</td>
    <td class="tg-0pky">0.3</td>
    <td class="tg-0pky"><span style="color:#FE0000">3.3</span></td>
    <td class="tg-0pky">-2</td>
  </tr>
  <tr>
    <td class="tg-0pky">s2</td>
    <td class="tg-36ox">1.3</td>
    <td class="tg-0pky">0.4</td>
    <td class="tg-0pky">-3</td>
  </tr>
  <tr>
    <td class="tg-0pky">s3</td>
    <td class="tg-0pky">0</td>
    <td class="tg-0pky">1.9</td>
    <td class="tg-36ox">2.4</td>
  </tr>
</tbody>
</table>

Initially, each entry in the table is 0 and Luigi learns to play by updating its Q-value. For each state it chooses the actions with the highest value. Then, the action and the state is passed to a referee that evaluates whether the move is legal or not. If it is illegal, the action receives a negative reward, i.e. the entry for this move on this state is updated using Bellman's Equation (Q-value decreases in this case). If the move is legal the new setup of the board is given and Luigi picks a new move. At the end of the game, each move that led to a win will receive a positive reward and a negative if the game was lost. Here is a simplified framework of the Algorithm.

![image](https://user-images.githubusercontent.com/35597877/137343416-3bc0f206-e242-4539-b84e-ae5b48262b00.png)



