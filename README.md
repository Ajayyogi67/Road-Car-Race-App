#🚗 Car Race Game in VB.NET

Welcome to the Car Race Game—a dynamic and engaging racing game developed using VB.NET. This project was built to showcase key aspects of game development, including speed management, collision detection, and user interaction.

#🎮 Game Overview

In this game, the player controls a car, navigating through a road filled with obstacles in the form of other cars. The objective is to avoid collisions and score points as you progress. The game gets progressively harder as the speed increases based on your score.

#🛠️ Features

* Speed Mechanics: The game dynamically adjusts the speed based on the player's score, increasing the challenge as you progress.
* Collision Detection: The game ends when the player's car collides with any of the other cars.
* Scoring System: The score increments as you successfully dodge the other cars.
* Responsive Controls: Use the arrow keys to move the car left or right.
* Replay Functionality: After the game ends, players can easily restart the game.

#📄 Code Explanation

Key Components
Speed Adjustment: The game speed is controlled using a speed variable, which increases as the score goes up, making the game more challenging.

If score > 10 And score < 20 Then speed = 5 End If If score > 20 And score < 30 Then speed = 6 End If If score > 30 Then speed = 8 End If

Collision Detection: The game checks for collisions between the player’s car (Car1) and the other cars (Car2, Car3, Car4, Car5) using Bounds.IntersectsWith. If a collision is detected, the game ends.

If (Car1.Bounds.IntersectsWith(Car2.Bounds)) Then Game_Over() End If

Game Over and Replay: When a collision is detected, the game stops, and a "Game Over" message is displayed. The player can then choose to replay the game.

Private Sub Game_Over() GameEnd.Visible = True RoadMove.Stop() right.Stop() left.Stop() Race1.Stop() Race2.Stop() Race3.Stop() Race4.Stop() Replay.Visible = True Total.Visible = True Points.Visible = False Total.Text = "TOTAL SCORE : " & score Label1.Visible = False End Sub

Obstacle Movement: The enemy cars move down the screen at varying speeds. Once they reach the bottom, they reappear at the top in a random position.

Private Sub Race1_Tick(sender As Object, e As EventArgs) Handles Race1.Tick Car2.Top += speed * 0.5 If Car2.Top >= Me.Height Then score += 1 Points.Text = "SCORE : " & score Car2.Top = -(CInt(Math.Ceiling(Rnd() * 80)) + Car2.Height) Car2.Left = CInt(Math.Ceiling(Rnd() * 10)) + 50 End If End Sub

Installation and Setup
To run the game locally:

Clone the repository: https://github.com/Ajayyogi67/Road-Car-Race-App.git

Open the project in Visual Studio:

Navigate to the project folder and open the .vbproj file in Visual Studio.
Build and Run:

Build the project and start the game by pressing F5.
Controls
Arrow Keys: Use the Left and Right arrow keys to move the car.
Screenshots
image image image image image image image image image

Future Improvements
Enhanced Graphics: Improving the visual quality of the game elements.
Sound Effects: Adding sound effects for collisions and gameplay actions.
Levels: Introducing multiple levels with increasing difficulty.
Contributing
If you'd like to contribute to this project, feel free to fork the repository and submit a pull request.
