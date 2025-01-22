# Go Race Condition Example

This repository demonstrates a common race condition in Go when multiple goroutines increment a shared variable without proper synchronization.

## The Problem
The `bug.go` file contains a program that launches 1000 goroutines, each incrementing a shared integer variable (`count`).  Because the increment operation (`count++`) is not atomic, data races can occur, leading to an incorrect final count (often less than 1000).

## The Solution
The `bugSolution.go` file provides a corrected version using a mutex to protect the shared variable, ensuring atomicity and preventing race conditions.  This guarantees that the final count will always be 1000.

## How to Run
1. Clone this repository.
2. Navigate to the repository directory.
3. Run the buggy program: `go run bug.go`
4. Run the corrected program: `go run bugSolution.go`

Observe the difference in output to understand the impact of race conditions and the importance of proper synchronization in concurrent Go programs.