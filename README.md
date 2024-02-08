# gravel
import pygame
import random


pygame.init()
screen = pygame.display.set_mode((800,800))
pygame.display.set_caption("gravel")

#create a buncha empty lists

sizes4 = []
positions4 = []
colors4 = []


#push a buncha numbers into the lists
for i in range(2500):
    sizes4.append(random.randrange(5,10)) #push in 1 number
    positions4.append((random.randrange(0, 800),random.randrange(0, 800))) #push in a 2-slot TUPLE
    colors4.append((random.randrange(0,255),random.randrange(0, 255),random.randrange(0,255))) #push in a 3-slot TUPLE
   
                                        #/\ This is the color.
while 1: #game loop###########################################################
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    #render section------------------------------
   
    screen.fill((0,0,0))# Clear the screen

    #draw the lines on the screen
    pygame.draw.line(screen, (255,255,255), (400, 0), (400, 800), 2)

    pygame.draw.line(screen, (255,255,255), (0, 400), (800, 400), 2)

    #draw the gravel

    for i in range(1000):
        pygame.draw.circle(screen, colors4[i], (positions4[i][0], positions4[i][1]), sizes4[i])
   
    pygame.display.flip()# Update the display

#end of game loop###################################################################
pygame.quit()
