1. Start
Concept: Program initialization
C syntax:
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    srand(time(NULL)); // seed for random agent choice
    
2. Display menu
Flowchart box: “vores display: (s) single player / (e) exit”
C syntax:
char choice;
printf("Vores display:\n(s) Single player\n(e) Exit\n");
scanf(" %c", &choice);

3. User input: choice
Decision logic: if player wants to play or exit
C syntax:
if (choice == 'e') {
    printf("Exiting game...\n");
    return 0;
}

4. Show shapes + user input
Flowchart box: “Show vores input: 🪨 ✂️ 🗒️ 🖖 🦎”
C syntax:
int user_shape;
printf("Select a shape:\n0🪨 1✂️ 2🗒️ 3🖖 4🦎\n");
scanf("%d", &user_shape);

5. Agent randomly chooses
Flowchart box: “the agent randomly choses”
C syntax:
int agent_shape = rand() % 5;

6. Compare inputs (game logic)
Flowchart box: “compare the results of inputs: … wins over …”
C syntax (example using if/else):
if (user_shape == agent_shape)
    printf("Draw!\n");
else if ((user_shape == 0 && (agent_shape == 1 || agent_shape == 4)) ||  // rock wins over scissors/lizard
         (user_shape == 1 && (agent_shape == 2 || agent_shape == 4)) ||  // scissors wins over paper/lizard
         (user_shape == 2 && (agent_shape == 0 || agent_shape == 3)) ||  // paper wins over rock/spock
         (user_shape == 3 && (agent_shape == 1 || agent_shape == 0)) ||  // spock wins over scissors/rock
         (user_shape == 4 && (agent_shape == 2 || agent_shape == 3)))    // lizard wins over paper/spock
    printf("You win!\n");
else
    printf("Agent wins!\n");

7. Check winner & end game
Flowchart box: “check winner” → “End game”
C syntax:
printf("Game over!\n");
return 0;
}



