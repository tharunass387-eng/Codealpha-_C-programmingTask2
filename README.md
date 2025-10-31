# Codealpha-_C-programmingTask2
Matrix operation 
# 📗 Matrix Operations using Functions and 2D Arrays

# Function to read a matrix from user
def read_matrix(rows, cols):
    matrix = []
    print(f"Enter the elements for a {rows}x{cols} matrix:")
    for i in range(rows):
        row = list(map(int, input(f"Row {i+1}: ").split()))
        while len(row) != cols:
            print(f"Please enter exactly {cols} values.")
            row = list(map(int, input(f"Row {i+1}: ").split()))
        matrix.append(row)
    return matrix


# Function to display a matrix
def display_matrix(matrix, name="Matrix"):
    print(f"\n{name}:")
    for row in matrix:
        print(" ".join(map(str, row)))


# Function for Matrix Addition
def add_matrices(A, B):
    rows, cols = len(A), len(A[0])
    result = [[A[i][j] + B[i][j] for j in range(cols)] for i in range(rows)]
    return result


# Function for Matrix Multiplication
def multiply_matrices(A, B):
    rows_A, cols_A = len(A), len(A[0])
    rows_B, cols_B = len(B), len(B[0])

    # Check for multiplication compatibility
    if cols_A != rows_B:
        print("Matrix multiplication not possible. Columns of A must equal rows of B.")
        return None

    # Initialize result matrix
    result = [[0 for _ in range(cols_B)] for _ in range(rows_A)]

    # Multiply
    for i in range(rows_A):
