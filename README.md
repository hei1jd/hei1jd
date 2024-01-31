# Initialize Pygame
pygame.init()
 
# Set up the display
width, height = 800, 600
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Simple Game")
 
# Set up colors
white = (255, 255, 255)
 
# Set up the player
player_size = 50
player_x = width // 2 - player_size // 2
player_y = height - 2 * player_size
 
# Set up clock to control the frame rate
clock = pygame.time.Clock()
 
# Main game loop
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()
 
    # Move player with arrow keys
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and player_x > 0:
        player_x -= 5
    if keys[pygame.K_RIGHT] and player_x < width - player_size:
        player_x += 5
 
    # Fill the screen with white
    screen.fill(white)
 
    # Draw the player
    pygame.draw.rect(screen, (0, 128, 255), (player_x, player_y, player_size, player_size))
 
    # Update the display
    pygame.display.flip()
 
    # Cap the frame rate
    clock.tick(60)
    
