# Problem 095 - Solution Summary

## Problem Description
This problem requires implementing permutation, cycle, and transposition operations in C++. These are fundamental concepts in group theory and combinatorics.

## Key Concepts

### Permutation
A mapping where position i gets the value from position mapping[i].
- Identity permutation: [0, 1, 2, ..., n-1]
- Multiplication: (p * q)[i] = p[q[i]]
- Inverse: inv[p[i]] = i

### Cycle
A rotation of elements in a circular pattern.
- Cycle {b0, b1, ..., bk-1} creates permutation where:
  - a(b0) = b1
  - a(b1) = b2
  - ...
  - a(bk-1) = b0

### Transposition
A special case of 2-cycle that swaps two positions.

## Implementation Details

### Memory Management
- Implemented copy constructors and assignment operators (Rule of Three)
- Proper dynamic memory allocation and deallocation
- All test points for memory management passed

### Key Methods
1. **Permutation::apply()**: Applies permutation to array
2. **Permutation::operator*()**: Multiplies two permutations
3. **Permutation::inverse()**: Computes inverse permutation
4. **Cycle::apply()**: Converts cycle to permutation then applies
5. **Transposition::apply()**: Swaps two positions

## Testing Results
- **Submission ID**: 766690
- **Status**: Accepted
- **Score**: 100.0/100.0
- **All 10 test cases passed**
- **Runtime**: ~3.1 seconds total
- **Memory**: ~47 MB maximum

## Lessons Learned
1. The critical fix was in the Cycle::apply() method - initially implemented as a direct swap, but needed to properly convert the cycle to a permutation first
2. Adding copy constructors and assignment operators was essential for proper memory management
3. Understanding the mathematical definitions was crucial - the cycle notation is about creating a permutation where elements rotate through positions

## Submission History
- Submission 1 (766682): Wrong Answer - Missing copy constructors
- Submission 2 (766684): Wrong Answer - Incorrect cycle apply logic
- Submission 3 (766690): Accepted - Fixed cycle apply implementation ✓
