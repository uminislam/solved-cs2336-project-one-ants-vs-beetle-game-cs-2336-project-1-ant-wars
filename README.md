Download Link: https://assignmentchef.com/product/solved-cs2336-project-one-ants-vs-beetle-game-cs-2336-project-1-ant-wars
<br>
<strong>Objective:</strong> Implement object-oriented programming in Java with inheritance and polymorphism. Problem: Mumbo Jumbo (a developer located in Dallas) has begun working on a new online game called Ant Wars. The game is a simple, casual game where players try to avoid their ant colony being destroyed by an invading colony of beetles. The player will have an opportunity to play against an AI or against another player. You have been assigned to help develop the AI part of the game.

<strong>Pseudocode:</strong> Your pseudocode should describe the following items

<ul>

 <li><strong>For each function, identify the following</strong>

  <ul>

   <li>Determine the parameters</li>

   <li>Determine the return type</li>

   <li>Detail the step-by-step logic that the function will perform</li>

  </ul></li>

 <li><strong>Functions</strong>

  <ul>

   <li><strong>Ant class</strong>

    <ul>

     <li>Breed</li>

     <li>Move</li>

    </ul></li>

   <li><strong>Beetle class</strong>

    <ul>

     <li>Breed</li>

     <li>Move</li>

     <li>Starve</li>

    </ul></li>

   <li><strong>Main class</strong>

    <ul>

     <li>Main</li>

     <li>Any additional functions that you plan to create</li>

    </ul></li>

  </ul></li>

</ul>

<strong>Classes</strong>

<ul>

 <li><strong>Base class</strong>

  <ul>

   <li>Name file Creature.java</li>

   <li>Creature</li>

   <li>Abstract class (-5 points if not)</li>

  </ul></li>

 <li><strong>Methods</strong>

  <ul>

   <li>Move (abstract) (-5 points if not)</li>

   <li>Breed (abstract) (-5 points if not)</li>

  </ul></li>

 <li><strong>Derived Classes</strong>

  <ul>

   <li><strong>Ant</strong>

    <ul>

     <li>Name file Ant.java</li>

     <li>Methods</li>

     <li>Move</li>

     <li>Breed</li>

    </ul></li>

   <li><strong>Beetle</strong>

    <ul>

     <li>Name file Beetle.java</li>

     <li>Methods</li>

     <li>Move</li>

     <li>Breed</li>

     <li>Starve</li>

    </ul></li>

  </ul></li>

 <li>You can add any member variables necessary for each class</li>

 <li>The main function must be in a file named Main.java</li>

</ul>

<strong>Details:</strong>

<ul>

 <li>The game will be played on a 10 x 10 grid

  <ul>

   <li>You decide how the grid will be stored in memory</li>

  </ul></li>

 <li>Beetles will move before the ants</li>

 <li>A file will be used to populate the grid

  <ul>

   <li>See sample file</li>

   <li>a = ant</li>

   <li>B = beetle</li>

  </ul></li>

 <li>Grid traversal should be by column first then row

  <ul>

   <li>Creatures to the left perform actions before creatures to the right</li>

  </ul></li>

 <li>User will specify number of turns to watch

  <ul>

   <li>There will not be any user interaction in the game</li>

   <li>The goal is to test the AI, so the game will play against itself</li>

  </ul></li>

 <li>All movement is orthogonal (N, S, E, W)

  <ul>

   <li>Movement is limited to one space per turn</li>

  </ul></li>

 <li>Movement happens before breeding and starving</li>

 <li>A beetle will eat an ant if it moves into the same space as the ant</li>

</ul>

<strong>Turn Order:</strong>

<ol>

 <li>Beetles move</li>

 <li>Ants move</li>

 <li>Beetles starve</li>

 <li>Ants breed</li>

 <li>Beetles breed</li>

</ol>

<strong>Ant Details:</strong>

<ul>

 <li><strong>Move</strong>

  <ul>

   <li>Each ant will move in the opposite direction of the nearest orthogonal beetle

    <ul>

     <li>If no orthogonal beetle, ant stands still</li>

     <li>If multiple beetles are nearest, prioritize movement</li>

    </ul></li>

   <li>Move ant in direction of no beetle if possible</li>

   <li>If beetles in all directions, move toward farthest beetle</li>

   <li>If there are multiple possible directions to move (either multiple clear pathways or multiple beetles furthest away) use the following movement priority: N, E, S, W

    <ul>

     <li>Ants cannot move to an occupied space</li>

    </ul></li>

   <li>If space moving to is occupied, no movement happens

    <ul>

     <li>Cannot move off grid</li>

    </ul></li>

  </ul></li>

 <li><strong>Breed</strong>

  <ul>

   <li>If ant survives 3 turns, it breeds</li>

   <li>Add ant in adjacent orthogonal space

    <ul>

     <li>Start with north space and check clockwise around space until empty orthogonal space found</li>

    </ul></li>

   <li>If no empty spaces, no breeding</li>

   <li>Ant may not breed again unless it survives another 3 turns</li>

  </ul></li>

</ul>

<strong>Beetle Details:</strong>

<ul>

 <li><strong>Move</strong>

  <ul>

   <li>Move toward nearest orthogonal ant</li>

   <li>If multiple ants are nearest prioritize movement</li>

   <li>Move toward ant with most adjacent ant neighbors (orthogonal and diagonal)</li>

   <li>If still tied, move toward ant with most ant neighbors using the following priority: N, E, S, W</li>

   <li>If no ant, move toward farthest edge</li>

   <li>If there is a tie for farthest edge, use the following priority: N, E, S W</li>

  </ul></li>

 <li><strong>Breed</strong>

  <ul>

   <li>If beetle survives for 8 turns, it breeds</li>

   <li>Use breeding algorithm for ants</li>

   <li>Beetle cannot breed again unless it survives another 8 turns</li>

  </ul></li>

 <li><strong>Starve</strong>

  <ul>

   <li>If a beetle does not eat an ant in 5 turns, it dies</li>

  </ul></li>

</ul>

<strong>User Interface:</strong> The user will be prompted for the following information in the order listed

<ul>

 <li>Initial grid filename</li>

 <li>Character to represent ant in output</li>

 <li>Character to represent beetle in output</li>

 <li>Number of turns</li>

</ul>

<strong>Input:</strong>

<ul>

 <li>The initial grid will be populated from file input.</li>

 <li>Prompt the user for the input filename

  <ul>

   <li>This would normally be hardcoded in an application, but zyLabs requires a filename for multiple test files</li>

  </ul></li>

 <li>There will be no need for input validation.</li>

 <li>Input sequence

  <ul>

   <li>Input file</li>

   <li>Ant character</li>

   <li>Beetle character</li>

   <li>Number of turns</li>

  </ul></li>

</ul>

<strong>Output:</strong>

<ul>

 <li>All output will be sent to the console.</li>

 <li>Print the current state of the grid to the console window for each turn.

  <ul>

   <li>Display the turn header followed by a blank line

    <ul>

     <li>TURN -space- -turn number-</li>

    </ul></li>

   <li>Display each row of the grid followed by a newline

    <ul>

     <li>Each ant and beetle is represented by the user-defined character</li>

     <li>An empty cell in the grid is represented with a space</li>

    </ul></li>

   <li>Display a blank line after the last row of the grid</li>

  </ul></li>

</ul>