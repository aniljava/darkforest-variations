# darkforest-variations

Script to generate different variations on each move from a SGF file using Facebook darkforest engine. 


# Current Status
- For each move, if it is different from the one suggested by the engine, a variation tree is generated upto depth `VARIATION_DEPTH`, (default 20).
- Resulting file is written in a output sgf file


# TODO
- Increase the number of variations from 1 branch each move to more depending on win rate on alternative branch
- Generate the branch on demand using comments
