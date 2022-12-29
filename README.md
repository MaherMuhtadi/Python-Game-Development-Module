# Python Game Development Module

## Description
This is a 2-D Game Development Module written in Python using the [PyGame](https://www.pygame.org/docs/) library. I created this module to define common and useful methods and attributes, encapsulated into _sprite_ class and _game_ class, for a simple game development experience.

### Features
1. Contains a _game_ class that can create a game window defined by the constructor parameters.
```
#Creating the snake game
from game_module import *
snake_game = game(title="Snake",
                  window_size=(560, 560),
                  background_path=r"images\background.png",
                  icon_path=r"images\icon.ico",
                  bg_music_path=r"audio\music.mp3",
                  fps=10)
```
2. Contains a _sprite_ class that creates a sprite from the constructor parameters.
3. The _sprite_ class contains methods to update the sprite, reset the sprite, create hitbox for the sprite, and draw the sprite on the game window.
4. The _game_ class contains methods to add sprites to the game.
5. The _game_ class contains a decorator method to add task functions to the game. These functions are called during every frame of the game.
6. Similar methods exist for adding event tasks and end tasks.
7. The _game_ class contains a `run` method to run the game loop.
8. Both classes contain attributes that can be used to retrieve information about the game and sprites.

## Installation

### Prerequisites
1. Download and install the latest version of [Python](https://www.python.org/downloads/) that is compatible with [PyGame](https://www.pygame.org/wiki/GettingStarted).
2. Check if python is properly installed along with its package installer using the following commands in your terminal:
```
$ python --version
$ python -m pip --version
```
3. If the Python package installer, pip, is not installed, get it installed using the [pip documentation](https://pip.pypa.io/en/stable/getting-started/).
4. Install the PyGame module by running the following command in your terminal:

    `pip install pygame`

### Usage
1. Download the repository as a ZIP or [clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) the repository to your local device.
2. Copy `game_module.py` to the root folder of your game project.
3. Import the file into the python scripts that need to use the module.
---
Last Updated: December 28, 2022