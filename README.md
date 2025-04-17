# Escape Room Process

## Overview
This BPMN diagram represents an Escape Room game process. Players attempt to escape a room within a time limit, with the possibility of achieving a high score and winning a prize.

## Process Flow

1. **Start**: The process begins when the Escape Room game is started.

2. **Escape the Room**: Players attempt to escape the room. This is a user task with a 2-minute time limit. A user simply needs to complete the form, but beware the form is haunted and spooky things tend to happen as you fill it out 👻

3. **Check Score**: After completing the room (within the time given), the system checks the player's score.

4. **High Score?**: The process then evaluates if the player achieved a high score. A high score it determined using a DMN table that evaluates how you filled in the form. 

   - If Yes: Proceeds to "Get Prize"
   - If No: Ends the process with "Escaped" status

5. **Get Prize**: For high scorers, the system retrieves a random fact as a prize.

6. **Collect Prize**: High-scoring players can collect their prize.

7. **End**: The process can end in three ways:
   - "Escaped": For players who complete the room but don't achieve a high score
   - "Escaped with High Score": For players who complete the room and achieve a high score
   - "You've failed to escape on time": If the 2-minute time limit is exceeded

## Additional Notes
- The process includes a timer event that triggers after 2 minutes, ending the game if the player hasn't escaped.
- The "Get Prize" task uses an HTTP connector to fetch a random fact from an external API.
- User forms are implemented for the "Escape the Room" and "Collect Prize" tasks.

## Deploying the Process

Once you clone this repo locally (or just copy all the files) you'll have two options

# One: Camunda Desktop Modeler
Open this as a process application in your desktop modeler, open up the BPMN file and use the desktop modeler deploy this to either SaaS or SM versions of Camunda

# Two: Camunda Web Modeler
Create a process application in the web modeler called `Escape Room` - You'll see it automatically greats a bpmn process called "Escape Room" that has a `main` tag - this is just a place holder for now.
Upload all of the `.bpmn`, `.dmn` and `.form` files to the process application. 
Find the `Escape Room Process` BPMN process and "Reasign as main Process".
Remove the auto-generated `Escape Room` process

Now open the `Escape Room Process` and click Deoploy
