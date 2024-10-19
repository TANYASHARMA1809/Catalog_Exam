## Problem Statement

In this assignment, you'll work on a simplified version of Shamir's Secret Sharing algorithm.

Consider an unknown polynomial of degree `m`. You would require `m + 1` roots of the polynomial to solve for the coefficients, represented as `k = m + 1`.

An unknown polynomial of degree `m` can be represented as:
f(x) = a_m * x^m + a_{m-1} * x^{m-1} + ... + a_1 * x + c


Where:
- `f(x)` is the polynomial function.
- `m` is the degree of the polynomial.
- `a_m, a_{m-1}, ..., a_1, c` are coefficients (real numbers).
- `a_m ≠ 0` (ensuring the polynomial is of degree `m`).

The task is to find the constant term `c` of the polynomial with the given roots provided in JSON format.

## Input Format

The input will be provided in JSON files with the following structure:

{
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    },
    "2": {
        "base": "2",
        "value": "111"
    },
    "3": {
        "base": "10",
        "value": "12"
    },
    "6": {
        "base": "4",
        "value": "213"
    }
}

The code implements a simplified version of Shamir's Secret Sharing algorithm as follows:

Required Modules:
const fs = require('fs');
This imports the fs module 


function decodeValue(base, valueStr) {
    return parseInt(valueStr, base);
}
Converts string of a number into an integer using the specified base.

Finding the Secret Constant:

function findSecretConstant(points) {
    // logic
}
Uses Lagrange interpolation to compute the secret constant c from the given points (roots).

Calculating the Secret:

function calculateSecret(jsonData) {
    // Logic extracting data from json
}
Extracts the number of points n and the minimum required points k, decodes the values, and computes the secret constant.

Processing Test Cases:

function processTestCase(filePath) {
    // reads JSON file and calculates secret
}
Reads a specified JSON file, calculates the secret using the decoded values, and logs the result.

Running the Test Cases:

processTestCase('input/testcase1.json');
processTestCase('input/testcase2.json');
