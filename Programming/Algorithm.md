# Algorithm

- https://www.youtube.com/watch?v=8hly31xKli0&list=WL&index=121
- https://cs50.harvard.edu/x/2022/weeks/3/

# Searching

## Linear Search

Time Complexity: O(n)
Space Complexity: O(n)

## Iterative Binary Search

Time Complexity: O(log(n))
Space Complexity: O(n)

## Recursive Binary Search

Time Complexity: O(log(n))
Space Complexity: O(nlog(n))

# Sorting

## Bogo Sort

Randomly rearrange list to make it sorted

## Selection Sort

1. Find the minimal number in the unsorted list and pop it off from the unsorted list
1. Add the minimal number to the sorted list
1. Repeat until there is no number in the unsorted list

## Bubble Sort

## Quick Sort

1. Split
   1. Find a number as pivot
   1. Split the unsorted list into small_than_pivot and large_than_pivot lists by comparing number to pivot

## Merge Sort

1. Split
   1. Find the midpoint number of the unsorted list
   1. Split the unsorted list into left and right lists based on the midpoint
1. Sort and Merge
