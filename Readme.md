# X14-Parts-Library

To create a new part:
1. Before you begin work, pull recent updates from the repo with:

	`git switch master`
	Or if you're old fashioned `git checkout master`.

	Then: `git pull`

2. Create a new branch for your part with (replace NEW_BRANCH_NAME with your own _new_ branch name):
	Make the branch name something descriptive like (Pi-Shield-Parts or Molex-nanofit)

	`git checkout -b NEW_BRANCH_NAME`

3. Make your changes in eagle to create the part.
	Name each part something descriptive (HMCA1305 does not immediately tell me anything about it).
	Each part should have the appropriate prefix first:
		- RES for resistor
		- CAP for capacitor
		- IND for inductor
		- CONN for connector
		- TRANS for transistor (mosfet, bjt, etc)
		- DIODE for diodes
		- IC for integrated circuits (muxes, microcontrollers, communication, etc.)
		- AUX for pre-made boards that we solder in with through holes (bricks, through hole linear regulators, IMUs, etc)
		- OTHER for other (mounting holes, etc)
	Download the datasheet for any part you make and save it with the part in the git repo and in the board's repo.

4. Getting rid of eagle's backup files:

	`git clean -n -X`  To see what files would be removed  
	`git clean -f -X`  To remove said files

5. Add you changes with:

	`git add .`

6. Commit your changes (this saves them) with (replace your message with an explanation of what was added):

	`git commit -m "YOUR MESSAGE"`
	ex: `git commit -m "Made the 4 pin molex 371/372 series miniclamp connector (part XXXX) for the backplane board."`

7. Push your changes to the remote repo with (use the same name as before):

	`git push`.
	If the branch was just created, do `git push -u origin NEW_BRANCH_NAME`
	
8. Open a pull request on [GitHub](https://github.com/purduerov/X13-Parts-Library/pulls) to merge your branch into master.
