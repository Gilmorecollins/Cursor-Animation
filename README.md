 ## Cursor-Animation

### Prerequisites

- Python 3.6 or later
- Pygame library

### Installation

1. Install Python 3.6 or later from https://www.python.org/downloads/
2. Install Pygame library using pip: `pip install pygame`

### Usage

1. Clone this repository: `git clone https://github.com/Gilmorecollins/Cursor-Animation.git`
2. Open a terminal window and navigate to the project directory: `cd Cursor-Animation`
3. Run the main script: `python main.py`

### Code Explanation

The code for this project is relatively simple and straightforward. Let's go through the main script `main.py` step by step to understand how it works:

```python
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set the screen size
screen = pygame.display.set_mode((800, 600))

# Create a clock object to control the frame rate
clock = pygame.time.Clock()

# Create a surface for the cursor
cursor_surface = pygame.Surface((32, 32))
cursor_surface.fill((255, 0, 0))  # Red color

# Create a cursor object
cursor = pygame.sprite.Sprite()
cursor.image = cursor_surface
cursor.rect = cursor_surface.get_rect()

# Set the initial position of the cursor
cursor.rect.center = (400, 300)

# Create a group for the cursor
cursor_group = pygame.sprite.Group()
cursor_group.add(cursor)

# Main game loop
while True:
    # Check for events
    for event in pygame.event.get():
        if event.type == pygame.QUIT:  # Close button clicked
            pygame.quit()
            sys.exit()

    # Update the cursor position
    cursor.rect.center = pygame.mouse.get_pos()

    # Draw the cursor
    screen.fill((0, 0, 0))  # Black background
    cursor_group.draw(screen)

    # Flip the display
    pygame.display.flip()

    # Cap the frame rate at 60 FPS
    clock.tick(60)
```
