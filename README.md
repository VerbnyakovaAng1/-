# -print("Морской бой")
import random
ship = [[0, 0], [0, 1], [0, 2], [0, 3]]
def random_board():
  global board
  x = random.randint(0, 4)
  y = random.randint(0, 4)
  a = random.randint(0, 1)
  if a == 0:
    board = [[x, y], [x, y+1], [x, y+2], [x, y+3]]
  else:
    board = [[x, y], [x+1, y], [x+2, y], [x+3, y]]
def show_pole():
    for line in pole:
        print('|'.join(line))
        print('-'*10)
        start(show_pole())
    def strelba():
        global paluba
        print("Ykazite stolbec")
        stolbec = int(input())
        print('Ykazite ryad')
        ryad = int(input())
        if [ryad, stolbec] in board:
            if pole[ryad][stolbec] != '#':
                print('Popal!')
                pole[ryad][stolbec] = '#'
                paluba = paluba - 1
                if paluba == 0:
                    print('Winner')
                else:
                    print('Mimo')
                    pole[ryad][stolbec] = '~'
                    show_pole()
                    random_board()
                    for i in range(10):
                        strelba()
                        show_pole()
