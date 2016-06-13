# darkforest-variations

Script to generate different variations on each move from a SGF file using Facebook darkforest engine. 

For each move, if it is different from the one suggested by the engine, a variation tree is generated upto depth `VARIATION_DEPTH`, (default 20).

`collections` folder has generated samples

# EXECUTING SCRIPT

Tested on Ubuntu 15.04

- Install torch and darkforestgo, for instructions see, https://github.com/facebookresearch/darkforestGo
- Edit, `start-nn-service` and `darkforest-gtp` to update the installation folders
- Run, start-nn-service as `./start-nn-service`
- run generator as `generator source.sgf dest.sgf`, replace source and dest sgf with actual sgf file names
- Once generated, stop the neural network service either as `killall luajit` or kill the process id using `ps aux`
- To change the variation depth from 20 to more or less, edit generator
- To change strength (Currently the time limit), edit generator

# TODO
- Increase the number of variations from 1 branch each move to more depending on win rate on alternative branch
- Generate the branch on demand using comments
- Copy existing variations from source file to the generated variation, currently only main branch and generated variations are saved on dest.
- Add metadata such as winrates, possible candidates without variations as a comment


# CONVENTIONS
- File name convention: `<event-detail>--<black-player>-vs-<white-player>--<optional-meta-info>.sgf` Eg: `ing-cup-semifinal-game-2--park-jungwhan-vs-lee-sedol.sgf`
- Player names from gokifu.com
