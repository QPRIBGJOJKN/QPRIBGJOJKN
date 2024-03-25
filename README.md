import pygame

pygame.init()
FPS = 60
WIDTH = 800
HEIGHT = 600
RED = (255, 0, 0)
ORANGE = (255, 128, 0)
BLUE = (0, 0, 255)
BLACK = (0, 0, 0,)


window = pygame.display.set_mode((WIDTH, HEIGHT))
clock = pygame.time.Clock()

run = True
while run:

    for i in pygame.event.get():
        if i.type == pygame.QUIT:
            run = False
        elif i.type == pygame.MOUSEBUTTONDOWN:
            if i.button == 1:
                pygame.draw.rect(window,BLUE,[i.pos[0],i.pos[1],10,10])
                print(i.pos)
            elif i.button == 3:
                pygame.draw.rect(window, BLACK, [i.pos[0], i.pos[1], 20, 20])

    pygame.display.update()
    clock.tick(FPS)


pygame.quit()
