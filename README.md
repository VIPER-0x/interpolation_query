# interpolation_query



**Explanation of the Code:**

This C# code implements a parallel search algorithm that searches for a target value in a sorted array from both ends simultaneously. Here's a breakdown of the key components:

1. **SearchForward Method:**
   - Searches the array from the start index to the middle index (forward direction).
   - Returns the index of the target value if found.
   - Uses a `CancellationToken` to support cancellation.

2. **SearchBackward Method:**
   - Searches the array from the end index to the middle index (backward direction).
   - Returns the index of the target value if found.
   - Uses a `CancellationToken` to support cancellation.

3. **Main Method:**
   - Initializes a sorted array and sets the target value.
   - Creates a `CancellationTokenSource` to manage cancellation.
   - Uses `Stopwatch` to measure the execution time of each search direction.
   - Launches both searches as parallel tasks using `Task.Run`.
   - Waits for the first task to complete using `Task.WhenAny`.
   - Cancels the other task once a result is found.
   - Prints the results and execution times.

**GitHub README File:**

```markdown
# Parallel Search in C\#

A parallel search implementation in C# that searches for a target value in a sorted array from both ends simultaneously. This approach leverages concurrency to potentially reduce the search time by dividing the work between two tasks.

## Features

- **Parallel Processing:** Searches from both ends of the array at the same time.
- **Cancellation Support:** Cancels the remaining search once the target is found.
- **Performance Measurement:** Tracks the execution time for each search direction.
- **Efficient Search:** Takes advantage of the array being sorted to optimize the search process.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ParallelSearch.git
   ```
2. Open the solution in Visual Studio or your preferred C# IDE.
3. Build the project to create the executable.

## Usage

1. Run the console application.
2. The program will search for the target value (default is 19) in the predefined sorted array.
3. The output will show:
   - The index where the element was found (if found).
   - The execution time for both the forward and backward searches.

Example Output:
```
Element found at index 5
Forward search time: 15 milliseconds
Backward search time: 12 milliseconds
```

## Code Explanation

### Key Components

1. **Search Methods:**
   - `SearchForward`: Searches from the start to the middle of the array.
   - `SearchBackward`: Searches from the end to the middle of the array.

2. **Main Function:**
   - Initializes the array and target value.
   - Uses `CancellationTokenSource` to manage task cancellation.
   - Measures execution time using `Stopwatch`.
   - Launches parallel tasks for both search directions.
   - Waits for the first task to complete and cancels the other task if needed.

3. **Concurrency and Cancellation:**
   - Uses `Task.Run` to run search methods in parallel.
   - Implements `CancellationToken` to stop the remaining search once the target is found.

## Benefits

- **Improved Performance:** By searching from both ends, the algorithm can potentially find the target faster.
- **Efficient Resource Usage:** Cancels unnecessary operations once the target is found.
- **Clear Execution Time Tracking:** Provides detailed timing information for each search direction.

## License

[MIT]
```

This README provides a clear overview of the project, its features, and how to use it. You can customize the content further based on your specific needs.
