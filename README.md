# ruby-assignment
<h1>Pinball Game</h1>

This is how the screen may look like:<br/>
|---------------|<br/>
|ㅤㅤㅤㅤㅤㅤ|<br/>
|ㅤㅤㅤㅤㅤㅤ|<br/>
|ㅤㅤㅤㅤㅤㅤ|<br/>
|ㅤㅤㅤㅤㅤㅤ|<br/>
|ㅤㅤ|ㅤ@ㅤㅤ|<br/>
|ㅤㅤ|ㅤㅤㅤㅤ|<br/>
| ----|ㅤㅤㅤㅤ|<br/>
|ㅤㅤ|ㅤㅤㅤㅤ|<br/>
|ㅤㅤ|ㅤㅤㅤㅤ|<br/>
|ㅤㅤㅤㅤㅤㅤ|<br/>
|ㅤㅤㅤㅤㅤㅤ|<br/>
|ㅤㅤㅤㅤㅤㅤ|<br/>
|ㅤㅤㅤㅤㅤㅤ|<br/>
|----====----|<br/>
<h2>Git - you need to create a local repository and make a few commits as you develop.</h2>
Your commits should have a descriptive message and there should be at least 5 of them, not all on a single day. After you are finished, you are expected to push your work to Git classroom (details will be provided shortly).

scored out of 3!
<h2>What you need to implement</h2>
You are given placeholder routines that make your application run in real time.
You need to write the following :
<br><br/>
***racquetLeft*** and racquetRight are the routines to update the position of the racquet when a player presses cursor keys left or right, respectively. You have to write these routines, keeping in mind that racquet should only move if its new position is entirely within the bounds of the play area.
scored out of 3
<br><br/>
***displayBoundaries*** displays the playing field from the screen array.
scored out of 3
<br><br/>
***displayDyn*** is responsible for displaying the ball and the racquet. It already displays the ball but you need to add code to it in order to display the racquet.
scored out of 3
<br><br/>
***update*** routine to take the position of a racquet and determine whether a ball is reflecting from a wall, a racquet or it was missed by a player. The routine should update $dx, $dy if a ball is reflected and return Nil if missed. The provided implementation simply updates the current coordinates of the ball assuming it does not bounce. It returns true/false values when a screen should be updated with a new position of the ball.
scored out of 4 for bounces from racquet
scored out of 4 for bounces from walls
<br><br/>
if the ball hits the racquet off-centre by 1 (this can be determined using the abs function such as x.abs for variable x), it should reflect from the racquet in a random direction. For this, use rand() to compute new $dx between -0.9 and 0.9 and adjust $dy so that the speed of the ball is mostly unaffected. The speed can be computed by taking a square root of $dx*$dx+$dy*$dy. If the new value of $dx is too large to maintain constant speed, choose $dy so that the ball does not speed up too much. You can use Math.sqrt to help you compute the new value of $dy.
scored out of 4
<br><br/>
count the number of times ball visits each cell on the screen. Cells that are visited more than 3 times during a game and more than 2% of the total number of visits of all cells should be painted with SC_STAR, denoting tracks left by the ball. For instance, if the ball travelled through 200 cells, 2% is 4 so any cell that is visited by the ball more than 4 times should have a star plotted in it (so long as it is not a wall cell). You can use global variables to store values of these counters. Once you paint a cell, you do not need to clear it if its use falls under 2%.
scored out of 6

<h2>Optional task: what you could do to make it easier to develop</h2>
update test code: when testmode is true, update should report the decisions it makes: for instance, it could display text LR when the ball bounces across a vertical wall and RND for a bounce in a random direction. Description which messages can be displayed when it runs are listed in the template code for tryupdate function. tryupdate is a test routine to check that update is working properly. You may find it useful to include a few tests for collisions of the ball with walls, racquet as well for the case where no collision is happening and the case where a ball misses the racquet (the game over case). The test could call tryupdate with coordinates of the ball and tryupdate would rely on update displaying its decisions. When doing such testing, trytest should be calling tryupdate with probably at least 8 values of x and y, reflecting testing of a bounce from a vertical wall from two sides, bounce from a horizontal wall from both sides, two bounces from a racquet (in the middle and off-centre) and a miss (where a racquet fails to stop a ball falling down). Case 8 is where no collision is happening.
