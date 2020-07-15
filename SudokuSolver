# This Sudoku solver solves a 9*9 sudoku, which should be input as a string os space separated 81 numbers, with zeroes in place of blank spaces

def print_grid(arr):
    for i in range(9):
        for j in range(9):
            print(arr[i][j], end=" ")
        print()

def used_in_row(arr,row,num):
    for i in range(9):
        if(arr[row][i] == num):
            return True
    return False

def used_in_col(arr,col,num):
    for i in range(9):
        if(arr[i][col] == num):
            return True
    return False

def used_in_box(arr,row,col,num):
    for i in range(3):
        for j in range(3):
            if(arr[i+row][j+col] == num):
                return True
    return False

def check_location_is_safe(arr,row,col,num):
    return not used_in_row(arr,row,num) and not used_in_col(arr,col,num) and not used_in_box(arr,row - row%3,col - col%3,num)

def find_empty_location(arr,l):
    for row in range(9):
        for col in range(9):
            if(arr[row][col]==0):
                l[0]=row
                l[1]=col
                return True
    return False

def solve_sudoku(grid):
    l=[0,0]
    if(not find_empty_location(grid,l)):
        return True
    row=l[0]
    col=l[1]
    for num in range(1,10):
        if(check_location_is_safe(grid,row,col,num)):
            grid[row][col]=num
            if(solve_sudoku(grid)):
                return True
            grid[row][col] = 0
    return False

if __name__ == '__main__':
    print('Please input your sudoku in a single line with zeroes at blank spaces')
    matrix = [[0 for i in range(9)] for i in range(9)]
    arr = list(map(int, input().strip().split()))
    t = 0
    for i in range(9):
        for j in range(9):
            matrix[i][j] = arr[t]
            t+=1
    if solve_sudoku(matrix):
        print_grid(matrix)
    else:
        print('Oops! the sudoku is invalid!')
