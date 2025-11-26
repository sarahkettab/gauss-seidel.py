def create_matrix():
    n = int(input("Enter number of rows: "))
    m = int(input("Enter number of columns: "))
    print("Enter the coefficients:")

    matrix = []
    for i in range(n):
        row = []
        for j in range(m):
            a = float(input(f"A[{i+1}][{j+1}] = "))
            row.append(a)
        matrix.append(row)

    print("\nMatrix A:")
    for row in matrix:
        print(row)

    return matrix


def create_vector_B(n):
    print("\nEnter values of vector B:")
    B = []
    for i in range(n):
        b = float(input(f"B[{i+1}] = "))
        B.append(b)

    print("\nVector B:", B)
    return B


def my_abs(x):
    if x >= 0:
        return x
    else:
        return -x


def sum_except_diagonal(row, diag_index):
    total = 0
    for j in range(len(row)):
        if j != diag_index:
            total += my_abs(row[j])
    return total


def check_conditions(A):
    print("\n=== Checking Diagonal Dominance ===")

    n = len(A)
    dominant = True

    for i in range(n):
        diag_value = my_abs(A[i][i])
        other_sum = sum_except_diagonal(A[i], i)

        print(f"\nRow {i+1}: |A[{i+1}][{i+1}]| = {diag_value} , sum(other) = {other_sum}")

        if diag_value >= other_sum:
            print("Row is dominant")
        else:
            print("Row is NOT dominant")
            dominant = False

    return dominant


def gauss_seidel(A, B, iterations):
    n = len(A)
    X = []
    for i in range(n):
        X.append(0)

    print("\n=== Starting Gauss-Seidel ===")

    for k in range(iterations):
        print(f"\n--- Iteration {k+1} ---")

        for i in range(n):
            s = 0
            for j in range(n):
                if j != i:
                    s = s + A[i][j] * X[j]

            X_new = (B[i] - s) / A[i][i]
            X[i] = X_new

        print("X =", X)

    return X


A = create_matrix()
B = create_vector_B(len(A))
check_conditions(A)
iterations = int(input("\nEnter number of iterations: "))
gauss_seidel(A, B, iterations)
