Download Link: https://assignmentchef.com/product/solved-eece-1080-lab4-game-of-chance
<br>
Gain experience with functions and modular program to promote code reuse.

<strong><u>Highlights</u></strong>:

<ul>

 <li>Please review chapter on functions</li>

 <li>Please read the specification below carefully.</li>

 <li>Review <strong>Grading Rubric</strong> at the end of this document.</li>

 <li>Review <strong>Sample Output</strong> at the end of this document.</li>

 <li>Please ask appropriate questions when necessary.</li>

 <li><em>To recieve full credit you will need to get Tasks 1 through 3 verified during the laborarory session. This will count towards your laboratory session attendance grade.</em></li>

 <li><em>Complete and have your program verified by the end of your scheduled laboratory session to recieve 10-bonus points.</em></li>

 <li>Your program should use <strong>at least 5 functions.</strong></li>

 <li>Your program source code should be formatted properly</li>

 <li>Your program should compile without warnings.</li>

 <li>Please submit the final result to blackboard for grading. The filename should be game.cpp.</li>

 <li><u style="font-size: 2em;">Specification:</u></li>

</ul>

Your program will run a simulation of a game of chance.  The code developed in this lab should all be a part of a single program.  Each task’s code will build upon previous tasks to create the final program at the end of task 5.  <strong><u>So you only have one program to submit at the end of this lab</u></strong>.

Consider the following simple dice game

<strong>Game Rules:</strong>

You pick a number from 1 to 6, and call this number your point.  You then roll a die 3 times.  If there is any match with your point, then you win $1; otherwise you pay the house $1.

<u>Program Development:</u>

You will be creating <strong><em>at least 5 functions</em></strong> to create this game program. Two of these functions will be <strong>rollDie()</strong> and <strong>playOneGame()</strong> as outlined in Tasks one through three below. The other three are your choice.

Some basic suggestions for functions might include the following:

<ul>

 <li>functions to perform input.</li>

 <li>functions to display statistics.</li>

 <li>a function to handle the complete logic of the program (move all or nearly all logic out of main())</li>

</ul>

The functions will need to make sense in the context of the program.

<strong>Notes</strong>:

<ul>

 <li>Avoid using non <strong><em>constant </em></strong>global variables.</li>

 <li>Source code should be properly formatted and consistently styled.</li>

 <li>You should comment the code appriopratiely.</li>

 <li>All program input should be verified for proper range of values. Have other users test your input.</li>

 <li>All program output should be probably formatted and readible. Have other students/users look at your output.</li>

</ul>

<h3>Task 1:</h3>

Design a program to simulate one play of this game. You will need a simple function <strong><em>rollDie() </em></strong>that returns a random integer in range 1-6. You should prompt for the point and roll the dice up to three times to see if you win/lose.




<table width="631">

 <tbody>

  <tr>

   <td width="631">Remember to utilize random numbers you need to do three things.

    <ol>

     <li>#include &lt;cstdlib&gt;</li>

     <li>#include &lt;ctime&gt;</li>

     <li>srand(time(NULL));   // Seed the random number, do this once, in main</li>

     <li>rand()   // Call rand to get a random number between 0 and INT_MAX</li>

    </ol></td>

  </tr>

 </tbody>

</table>




The rand() function does not take any parameters and returns an integer between 0 and 32K. You will need to use the modulus operator to scale it down to numbers between 1 and 6.

<h3>Task 2:</h3>

If your game works correctly you should then design a loop control structure that keeps repeating the game, and tracks the number of wins and losses. The loop should continue until the user enters in an appropriate sentinel value, such as the character ‘x’ for exit. Verify that the program runs properly, and as expected, before continuing.

<h3>Task 3:</h3>

Modify the code so that you encapsulate the logic of the game into a single function. The function should have a prototype:

<strong><em>bool playOneGame() </em></strong>

The function should return true if the game is won by the user, and returns false if the game is lost. Note that you do not need to change the basic logic of the original program to design your function.  Test your function with a driver program that prints the results of the function call.

<h3>Task 4:</h3>

Modify the program so that the user is able to maintain a bank account (which is initialized with $100.00) and wager on each play. The program should prompt the user to enter a wager.  This wager replaces the simple case of winning/losing $1 from before. Do an error check (using a while loop), so that the wager entered is no more than the current bank balance. If the wager is valid, then inform the user that they will be playing a single game. If the wager is invalid, print an error message and repeat the process.

<h3>Task 5:</h3>

A play of a single game is made by calling the function you created in Task 2. A win (return value true by function playOneGame()) will increase the bank balance by the wager, and likewise a lose (return value of false by function <strong><em>playOneGame()</em></strong>) will decrease the balance by same. After the game is played, print the current balance in an appropriate format. If the balance is greater than zero, prompt the user to play again. Continue another round of the game until the user responds that the user finishes playing (by wagering 0), or if the user’s balance is zero.

After the game is over you should print out the number of games won or lost, and the percentage of games won. You may want to create a function to output these statistics.

Task 6:

<h3>Example Program Run</h3>

Remember – randomization is in effect here, so subsequent runs will not have the same exact result.







<table width="576">

 <tbody>

  <tr>

   <td width="576">Account balance $100Enter wager (0 to exit): 50 Enter your point value (1 – 6): 1Roll #1 is 1** You win! **Account balance $150Enter wager (0 to exit): 50 Enter your point value (1 – 6): 1Roll #1 is 5Roll #2 is 4Roll #3 is 5** You Lose **Account balance $100Enter wager (0 to exit): 50 Enter your point value (1 – 6): 1Roll #1 is 4Roll #2 is 2Roll #3 is 6** You Lose **Account balance $50Enter wager (0 to exit): 50 Enter your point value (1 – 6): 1Roll #1 is 5Roll #2 is 1** You win! **Account balance $100Enter wager (0 to exit): 100 Enter your point value (1 – 6): 5Roll #1 is 4Roll #2 is 2Roll #3 is 6** You Lose **Game over, you are out of money!Your final account balance is $0You won 1 time out of 4 for a winning percentage of 25% </td>

  </tr>

 </tbody>

</table>




Another sample run, where the user wagers 0 to exit.




<table width="576">

 <tbody>

  <tr>

   <td width="576">Account balance $100Enter wager (0 to exit): 75 Enter your point value (1 – 6): 4Roll #1 is 2Roll #2 is 4** You win! **Account balance $175Enter wager (0 to exit): 0Your final account balance is $175You won 1 time out of 1 for a winning percentage of 100%  </td>

  </tr>

 </tbody>

</table>




And, another sample run, with input errors.




<table width="576">

 <tbody>

  <tr>

   <td width="576">Account balance $100Enter wager (0 to exit): -4Error: You must wager between $1 and $100 (type 0 to exit): 101Error: You must wager between $1 and $100 (type 0 to exit): 45 Enter your point value (1 – 6): -1Error: Enter your point value, must be between 1 and 6: 1723Error: Enter your point value, must be between 1 and 6: 234Error: Enter your point value, must be between 1 and 6: 7Error: Enter your point value, must be between 1 and 6: 6Roll #1 is 3Roll #2 is 1Roll #3 is 3** You Lose **Account balance $55Enter wager (0 to exit): 0Your final account balance is $55You won 0 time out of 1 for a winning percentage of 0%  </td>

  </tr>

 </tbody>

</table>







<strong> </strong>