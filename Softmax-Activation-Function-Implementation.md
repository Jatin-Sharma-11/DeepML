# Softmax Activation Function Implementation

## Problem Statement

Write a Python function that computes the softmax activation for a given list of scores. The function should return the softmax values as a list, each rounded to four decimal places.

### Description
The softmax function converts a list of values into a probability distribution. The probabilities are proportional to the exponential of each element divided by the sum of the exponentials of all elements in the list.

### Example
Input: scores = [1, 2, 3]
Output: [0.0900, 0.2447, 0.6652]
Explanation:

Compute exponentials: e^1 ≈ 2.7183, e^2 ≈ 7.3891, e^3 ≈ 20.0855
Sum of exponentials: 2.7183 + 7.3891 + 20.0855 ≈ 30.1929
Softmax values:
e^1 / sum ≈ 2.7183 / 30.1929 ≈ 0.0900
e^2 / sum ≈ 7.3891 / 30.1929 ≈ 0.2447
e^3 / sum ≈ 20.0855 / 30.1929 ≈ 0.6652
Result: [0.0900, 0.2447, 0.6652] (rounded to 4 decimal places)


## Solution

### Code
```python
import math

def softmax(scores: list[float]) -> list[float]:
    # Compute exponentials of all scores
    exp = [math.exp(i) for i in scores]
    # Sum of all exponentials
    exp_sum = sum(exp)
    # Calculate softmax probabilities and round to 4 decimal places
    probabilities = [round(e / exp_sum, 4) for e in exp]
    return probabilities

# Test the function
if __name__ == "__main__":
    scores = [1, 2, 3]
    result = softmax(scores)
    print(result)  # Output: [0.0900, 0.2447, 0.6652]
