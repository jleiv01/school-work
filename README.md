# Path-of-the-Jaguar

Challenge 1 from ACM
=======================
In this challenge, create a game where you fight against creatures and use special abilities based on the type of character you create! Here are the following rules, get as far as you can! In this challenge, we are focusing only on character creation, and combat!

1. Create an introduction to the user starting the game. The name of the game is "Path of the Jaguar".

2. Create an interface called SpecialAbility
   - Have a method for pressingAttack, sneakAttack, magicDart, flameSweep, and lightningBolt
   - Implement this interface into the class "Combatant" (described next)

3. The character will need to have hit points (amount of life), an armor class (a value to prevent getting hit), a weapon (determined by their profession), and a level
   -	Extend the Abstract Class Player, and extend it into another Class called Combatant
   -	Integrate all instance (private) variables, the constructor, and the methods
   -	Create logic for the profession in the constructor
         - If a Fighter, the starting armor class is 17, rogue a 15 armor class, and wizard a 13 armor class
         -	A fighter gets the sword that does d8 damage (d8 is an 8-sided die, we'll need to randomize this when attacking!), the rogue gets a shortsword (d6), and the wizard gets a staff (d4)
         -	Each profession gets a special ability, the Fighter gets pressingAttack, rogue gets sneakAttack, and Wizard gets magicDart, flameSweep, and lightningBolt
   -	Create logic for the races in the constructor
         -	If human, the starting hit points should be 100, if elven, only 80 hit points, if dwarven, 120 hit points.
         -	Elves get a + 1 to armor class, dwarves get a -1 to armor class
   -	All characters will start at level 1

4.	 Have a getter for current hit points

5. Under the attack method, have a randomizing attack that rolls a d20, here are the rules of combat:
   -	Character can only attack while alive
   -	Character rolls a d20 (20-sided die, you’ll need a randomizer for this) to see if they hit against the target’s armor class, if the roll matches the armor class, it still hits, anything below it is a miss
         -	Hint: If I roll a 16 and the enemy’s armor class is a 16, you hit. Though, if I roll a 15, it’s a miss
   -	If the attack doesn’t strike, have a print statement saying the name of the character, what they rolled, and that they missed
   -	If the attack does strike, conduct logic for the damage based on the weapon the character has, this must be randomized! If a rogue is attacking, they have to roll a d6 to see how much damage they do! Deduct this from the target’s hp; also have a print statement with the character’s name, the attack roll, the damage done, and the target being hit
   -	If the attack roll is a natural 20, that means you crit! Have the damage roll be multiplied by 3 to reflect this! Also make the print statement with the name of the character, the attack roll, with the word “CRITS” in it, and the amount of damage done, with the name of the target (i.e. Artemis rolls a 20 and CRITS Hector for 30 damage!)
   -	Elves get a -1 to damage, and dwarves get a +1 to damage

6. Define the search method
   -	If a monster is dead, have the character search, or “loot”, the dead monster
   -	The search can only happen one time, and it can only be done if the monster is dead
   -	Create logic for the character to find a healing potion on 20% of their searches
   -  In the case a character does find a potion, have it heal them for 2d6 + 2

7. BONUS (read below): Define Special Abilities from the implemented SpecialAbility Interface
   -	The pressingAttack is a Fighter specific ability, it can only be used twice per game
         -	The pressingAttack method increases the Fighter’s odds of hitting by adding a +5 to the attack roll, and if the strike succeeds, it does an extra die of damage (in the case of a longsword being 1d8, the Fighter will do 2d8)
   -	The sneakAttack is a rogue specific ability, it can be used three times per game
         -	The sneakAttack method increases the rogue’s attack roll by + 3, but it does an additional 2 dice worth of damage (i.e. from 1d6 to 3d6)
   -	The magicDart, flameSweep, and lightningBolt are wizard specific abilities, the first two can be used 3 times each, and the last one only once (each one of these attacks are not stacked with the staff, they are mutually exclusive)
         -	The magicDart method gives a +10 to attack, and does 4d4 to damage (four 4-sided dice)
         -	The flameSweep method gives a +8 to attack, and does 3d6 to damage (three 6-sided dice)
         -	The final method, lightningBolt gives a +12 to attack and does 8d6 to damage (eight 6-sided dice)
   -	Keep in mind, you need to be creative on how this works, you need to tie this to the character, which means you may need to append to the constructor to allow this to happen!

8. Create rules for an orc race!
   -	The orc race will be the monsters you fight
   -	Orcs starting hitPoints are 75
   -	Orcs get a +3 to attack and damage rolls
   -	Orcs armor class is 16
   -	Orcs do not have special abilities! They are orcs!

9. On your main driving class, create a while loop that will cycle through the combat
   -	Have the character and the Orc created
   -	Cycle through combat turn by turn, each turn the combatants attack each other
   -	When one combatant is killed, end the loop
   -	Declare the victor with a printed victory statement

<h3>Other instructions:</h3>

   -	This is a challenge, and meant to be slightly difficult to understand concepts of Object Oriented Programming
   -	Document your name and date on your program (in comments on the top of main)
   -	Speaking of commenting, they are useful! Practice them and use them as reminders for yourself, and for other professors to see them!
   - For the battle, use a While(True) loop, learn to use continue and break
   -	Use git, it allows you to clone our framework code, and back them up to your own private repos! Not familiar? Read up on it! ACM has some notes on JagSync!

<h3>Bonuses:</h3>

   -	Do step 7, this isn’t required, but if this step is done, you must also add user entry in the combat loop, allowing players to choose if they want to do a regular attack, or a special ability, remember, there are limits to how many special abilities you can use
   -	Make all aspects of the game user entry, so that the game isn’t automatic, it’s driven forward by the users choices, from the menu, a character can do the following:
         -	Check their hit points (this does not end their turn)
         -	Attack
         -	Use special ability
         -  Drink a potion (found from looting/searching method, that means searching method doesn't automatically make the character use it)
         -	Or retreat (which ends the combat)
         - NOTE: You'll need methods for drinking potion and retreating
   -	Have an endless fight, after each Orc is slain, generate another Orc automatically and see how many your character can push through
   -	Create an Ogre race, here are the details:
         -	Starting hit points 125 hit points
         -	Armor class is a 13
         -	Ogres get +4 to attack, and +6 to damage
         -	Ogres have a special ability they use called “Smash”
            - Create the smash method that the Ogre uses on every 4 rounds
            - Orge get +6 to attack, and +10 to damage
            - Have the Ogre yell out “SMASH!!!” every time this method is used
   -	Using switch statements instead of if/else
   -	Any other creative aspects you take will be taken into account!
