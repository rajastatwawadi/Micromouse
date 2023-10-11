# Micromouse
This is the official repository for the Micromouse project at IvLabs, VNIT Nagpur

## Objectives
The objectives of the summer internship were to create a compact robot that could autonomously solve any given maze. 

## Methodology
In the initial first weeks, we worked on implementing the software algorithms. We tried a set of algorithms, namely

1.Wall Following

![unnamed](https://github.com/ChinmayK0607/Micromouse/assets/114411195/c75196c7-b359-4f6c-813e-1bdc06cc3916)



2.BFS

![unnamed (2)](https://github.com/ChinmayK0607/Micromouse/assets/114411195/5c1c0090-bf98-4234-b390-1e8a5d37e98b)


3.DFS

![unnamed (1)](https://github.com/ChinmayK0607/Micromouse/assets/114411195/9875c933-78fc-4c69-aba6-03c77bc93ab8)


4.Flood Fill

![unnamed (3)](https://github.com/ChinmayK0607/Micromouse/assets/114411195/fdd92060-7501-4717-bc51-6b367a332059)



Code for each of the above mentioned can be found in ```Algorithmic Implementations``` Folder.

After this, we built a maze using corrugated sheets and started working on the hardware parts inclulding sensor testing and assembly.


![image](https://github.com/ChinmayK0607/Micromouse/assets/114411195/ae7f2db2-d7bf-4d09-bff6-167788ed4e04)


The detailed hardware breakdown is mentioned below. 

We went with using sensor data for precise turning, and we were able to solve the maze.
Testing included 5 different mazes.

Image of the final bot:


![image](https://github.com/ChinmayK0607/Micromouse/assets/114411195/ec0dbd74-119c-4425-928d-b187f86c4505)


## Hardware Explanation
Here is a both high level and low level diagram for understanding of the hardware implementation
![image](https://github.com/ChinmayK0607/Micromouse/assets/114411195/6be8035b-0604-475b-956f-26d8a51b0aa2)

![image](https://github.com/ChinmayK0607/Micromouse/assets/114411195/b1fa66ec-f1b0-48fe-924e-58f44655b7bf)


The circuit overall is controlled by the Arduino nano. 

The code for movement and speed control as well for maintaining a particular distance from the wall is uploaded in the Arduino nano.
It analyzes the data sent by the motor encoders and calculates the distance covered accordingly. 

It also reads the data from all the three ultrasonic sensors and gives output to the motor so that the bot maintains a particular distance from the wall.

The motor driver receives the input from the Arduino nano and accordingly supplies the signal to the motor so that the motor can perform the required movement.

The circuit drives its power from a 7.4V LiPo batttery.

The connections of the circuit are as shown in the circuit digram above.


## Software Explanation

Since the initial simulations were in python, we had to create data structures for the maze map and directions. We implemented flood fill as the final algorithm as it was the fastest comparitively and gave good results.

How it works:
The flood fill is an optimistic search algorithm that can help in solving mazes, it simulates water flooding a maze and reaching the goal and thus the name. 

It initially assumes that there are no walls and generates a first maze map using bfs/dfs. A maze map considers the goal as 0 and each preceding cell has value one more than the earlier cell.

Example : ``` current_cell.value() = previous_cell.value()+1 ; ```

Flood fill video:

![Untitled video - Made with Clipchamp (5)](https://github.com/ChinmayK0607/Micromouse/assets/114411195/2238fc76-befa-4fdc-a332-68aed780f492)




The mouse then runs once to generate a maze map according to intial run.
It then backtracks using a different path and then decides the shortest path based on these two runs.

Link to extensive breakdown of code: https://hackmd.io/@l_WDq7lkQq29Pz-KD1JPNA/HkYDExRTh


## How to run the code
Download the arudino ide and run the files.

For simulation:
``` pip install pyamaze```

Then you are good to go
