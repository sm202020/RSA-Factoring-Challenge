#!/usr/bin/python3

import sys
import time

def factorize(num):
    '''
    Takes a number as input and returns its factors if it's not a prime, or None if it's prime.

    Args:
        num (int): Input integer.

    Returns:
        tuple or None: A tuple of two factors if the number is not a prime, None if the number is prime.
    '''
    for i in range(2, int(num**0.5)+1):
        if num % i == 0:
            return (i, num//i)
    return None

if __name__ == "__main__":
    '''
    Reads the input file and processes each line.

    Usage: factors <file>
    '''
    if len(sys.argv) != 2:
        print("Usage: factors <file>")
        exit()

    input_file = sys.argv[1]

    try:
        with open(input_file, 'r') as f:
            lines = f.readlines()
    except FileNotFoundError:
        print("File not found")
        exit()

    start_time = time.time()

    '''
    Loops over each line (which should contain one natural number per line) and calls factorize on each number.
    If factorize returns a tuple of factors, it prints the factorization in the desired format.

    If the elapsed time exceeds 5 seconds, the program exits with an error message.
    '''
    for line in lines:
        num = int(line.strip())
        factors = factorize(num)
        if factors:
            print(f"{num}={factors[0]}*{factors[1]}")

        if time.time() - start_time > 5:
            print("Time limit exceeded")
            exit()
