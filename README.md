# AnimalAI 3

AAI supports interdisciplinary research to help better understand human, animal, and artificial cognition. It aims to support AI research towards unlocking cognitive capabilities and better understanding the space of possible minds. It is designed to facilitate testing across animals, humans, and AI.

| ![](docs/figs/animal-cyl-fail.gif) | ![](docs/figs/agent-cyl-fail.gif) |
|---|---|
| ![](docs/figs/animal-cyl-pass.gif) | ![](docs/figs/agent-cyl-pass.gif) |

## This Repo

This repo contains the AnimalAI environment, some introductory python scripts for interacting with it, as well as the [900 tasks](competition_configurations) which were used in the original Animal-AI Olympics competition (and some others for demonstration purposes). Details of the tasks can be found on the [AAI website](http://animalaiolympics.com/AAI/testbed) where they can also be played and competition entries watched.

The environment is built using [Unity ml-agents](https://github.com/Unity-Technologies/ml-agents/tree/master/docs) release 2.1.0-exp.1 (python version 0.27.0).

The AnimalAI environment and packages are currently only tested on linux (Ubuntu 20.04.2 LTS) with python 3.8 but have been reported working with python 3.6+, other linux distros and Windows and Mac.

**The Unity Project** for the environment is available [here](https://github.com/mdcrosby/animal-ai-unity-project).


## Installing

To get started you will need to:
1. Clone this repo.
2. **Install the animalai python package** and requirements by running `pip install -e animalai` from the root folder.
3. **Download the environment** for your system:

| OS | Environment link |
| --- | --- |
| Linux |  [v3.0](http://mdcrosby.com/builds/AnimalAI_LINUX_3.0.zip) |
| Mac | [v3.0](http://mdcrosby.com/builds/AnimalAI_MAC_3.0.zip) |
| Windows | [v3.0](http://mdcrosby.com/builds/AnimalAI_WINDOWS_3.0.zip) |

Unzip the **entire content** of the archive to the (initially empty) `env` folder. On linux you may have to make the file executable by running `chmod +x env/AnimalAI.x86_64`. Note that the env folder should contain the AnimalAI.exe/.x86_84/.app depending on your system and *any other folders* in the same directory in the zip file.

## Tutorials and Examples

Some example scripts to get started can be found in the `examples` folder. The following docs provide information for some common uses of the environment.

- [Getting started with the environment](docs/quickStart.md)
- [Using the ML-Agents Low-Level API: A hand-coded Braitenberg Vehicle baseline](docs/lowLevelAPI.md)
- [Designing Experiments](docs/configFile.md)
- [Training examples](docs/training.md)

## Manual Control

If you launch the environment directly from the executable or through the `play.py` script it will launch in player mode. Here you can control the agent with the following:

| Keyboard Key  | Action    |
| --- | --- |
| W   | move agent forwards |
| S   | move agent backwards|
| A   | turn agent left     |
| D   | turn agent right    |
| C   | switch camera       |
| R   | reset environment   |

## Citing
If you use the Animal-AI environment in your work you can cite the environment paper:

 Crosby, M., Beyret, B., Shanahan, M., Hernández-Orallo, J., Cheke, L. & Halina, M.. (2020). The Animal-AI Testbed and Competition. Proceedings of the NeurIPS 2019 Competition and Demonstration Track, in Proceedings of Machine Learning Research 123:164-176 Available [here](http://proceedings.mlr.press/v123/crosby20a.html).
```
 @InProceedings{pmlr-v123-crosby20a, 
    title = {The Animal-AI Testbed and Competition}, 
    author = {Crosby, Matthew and Beyret, Benjamin and Shanahan, Murray and Hern\'{a}ndez-Orallo, Jos\'{e} and Cheke, Lucy and Halina, Marta}, 
    booktitle = {Proceedings of the NeurIPS 2019 Competition and Demonstration Track}, 
    pages = {164--176}, 
    year = {2020}, 
    editor = {Hugo Jair Escalante and Raia Hadsell}, 
    volume = {123}, 
    series = {Proceedings of Machine Learning Research}, 
    month = {08--14 Dec}, 
    publisher = {PMLR}, 
} 
```

## Unity ML-Agents

The Animal-AI Olympics was built using [Unity's ML-Agents Toolkit.](https://github.com/Unity-Technologies/ml-agents)

Juliani, A., Berges, V., Vckay, E., Gao, Y., Henry, H., Mattar, M., Lange, D. (2018). [Unity: A General Platform for 
Intelligent Agents.](https://arxiv.org/abs/1809.02627) *arXiv preprint arXiv:1809.02627*

Further the documentation for [mlagents](https://github.com/Unity-Technologies/ml-agents) should be consulted if you want to make any changes.

## Version History

- v2.2.3
  - Now you can specify multiple different arenas in a single yml config file ant the environment will cycle through them each time it resets
- v2.2.2 
  - Low quality version with improved fps. (will work on further improvments to graphics & fps later)
- v2.2.1
  - Improve UI scaling wrt. screen size
  - Fixed an issue with cardbox objects spawning at the wrong sizes
  - Fixed an issue where the environment would time out after the time period even when health > 0 (no longer intended behaviour)
  - Improved Death Zone shader for weird Zone sizes
- v2.2.0 Health and Basic Scripts
  - Switched to health-based system (rewards remain the same).
  - Updated overlay in play mode.
  - Allow 3D hot zones and death zones and make them 3D by default in old configs.
  - Added rewards that grow/decay (currently not configurable but will be added in next update).
  - Added basic Gym Wrapper.
  - Added basic heuristic agent for benchmarking and testing.
  - Improved all other python scripts.
  - Fixed a reset environment bug when resetting during training.
  - Added the ability to set the DecisionPeriod (frameskip) when instantiating and environment.
- v2.1.1 bugfix
  - Fixed raycast length being less then diagonal length of standard arena
- v2.1 beta release
  - Upgraded to ML-Agents release 2 (0.26.0)
  - New features
    - Added raycast observations
    - Added agent global position to observations
