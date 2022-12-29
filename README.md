<div align="center">

# Python Game Development Module

</div>

## Description
This is a 2-D Game Development Module written in Python using the [PyGame](https://www.pygame.org/docs/) library. I created this module to define common and useful methods and attributes, encapsulated into _sprite_ class and _game_ class, for a simple game development experience.

### Features
1. Contains a _game_ class that can create a game window.
```py
from game_module import *

#Creating the mouse game
mouse_game = game(title="mouse",
                  window_size=(560, 560),
                  color=(0, 0, 0),
                  background_path=r"images\background.png",
                  icon_path=r"images\icon.ico",
                  bg_music_path=r"audio\music.mp3",
                  fps=10)
```
2. Contains a _sprite_ class that creates a game sprite.
```py
# Creating a mouse sprite for the game
mouse = sprite(image_path=r"images\mouse.png",
               initial_x=384,
               initial_y=264,)
```
3. The _sprite_ class contains methods to update the sprite, reset the sprite, create hitbox (pygame.Rect object) for the sprite on the game window.
```py
# Repositions the sprite to (0,0) coordinates on the window
mouse.update_position(new_x=0, new_y=0)

# Moves the sprite to the left by 1 pixel
mouse.change_postion(x_change=-1, y_change=0)

# Stores a skin for the sprite
mouse.add_image(key="bonus", image_path=r"images\bonus.png")

# Changes the skin of the sprite
mouse.change_image(key="bonus")

# Resets the skin of the sprite
mouse.change_image(key="default")

# Returns a hitbox of size 32x32 px
hitbox = mouse.rectangle(width=32, height=32)

# Resets the sprite to original coordinates and skin
mouse.reset()
```
4. The _game_ class contains a method to add sprites to the game.
```py
mouse_game.add_entity(mouse)
```
5. The _game_ class contains a decorator method to add task functions to the game. These functions are called during every frame of the game (each iteration of the game loop).
```py
def move_mouse():
    '''moves mouse left by 1px'''
    mouse.change_postion(x_change=-1, y_change=0)

# call move_mouse() every iteration of the game loop
mouse_game.add_task(move_mouse)
```
6. Similar methods exist for adding event tasks and end tasks.
```py
def down_key_action(event):
    '''moves down when down key is pressed'''
    if event.type == pygame.KEYDOWN:
        mouse.change_postion(x_change=0, y_change=5)

# call down_key_action(event) with each pygame event in every iteration of the game loop
mouse_game.add_event_task(down_key_action)

def save_score():
    '''saves score to an external file'''
    saved_record = open("score.txt", "w")
    saved_record.write(str(score))
    saved_record.close()

# call save_score() when the game is quit
mouse_game.add_end_task(save_score)
```
7. The _game_ class contains a `run` method to start the game (run the game loop).
```py
mouse_game.run()
```
8. Both classes contain attributes that can be used to retrieve information about the game and sprites.

For more information, look inside the module file.

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

For a demonstration of its usage, check out my [Snake Game](https://github.com/MaherMuhtadi/Snake-Game).

---
Last Updated: December 29, 2022