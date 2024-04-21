# EDIT AI/ML TECHNICAL QUESTIONS FOR SKILLS DEVELOPMENT TRACK

## Overview
This document contains my responses to my EDIT AI/ML Internship application's technical questions. Below are my solutions to the provided problems, using Python and R.

## Questions and Responses

### 1. Functional Programming in Python and R
**Question:** Write functions in Python and R to calculate the mean, standard deviation, and count of elements in a list/vector.

- **Python Code:**
    ```python
    def compute_stats(data):
        mean_val = sum(data) / len(data)
        variance = sum((x - mean_val) ** 2 for x in data) / len(data)
        std_dev = variance ** 0.5
        return mean_val, std_dev, len(data)

    # Example data
    data = [5.99, 4.72, 6.29, 8.04, 4.53, 4.53, 8.15, 6.53, 4.06, 6.08]
    results = compute_stats(data)
    print("Mean:", results[0], "Standard Deviation:", results[1], "Count:", results[2])
    ```

- **R Code:**
    ```r
    compute_stats <- function(data) {
      mean_val <- mean(data)
      std_dev <- sd(data)
      count <- length(data)
      return(c(mean=mean_val, sd=std_dev, count=count))
    }

    # Example data
    data <- c(5.99, 4.72, 6.29, 8.04, 4.53, 4.53, 8.15, 6.53, 4.06, 6.08)
    results <- compute_stats(data)
    print(results)
    ```

### 2. Statistical Analysis in Python
**Question:** Calculate the proportion of gene expression values above a threshold.
- **Python Code:**
    ```python
    data = [5.99, 4.72, 6.29, 8.04, 4.53, 4.53, 8.15, 6.53, 4.06, 6.08]
    threshold = 4
    proportion_above_threshold = sum(x > threshold for x in data) / len(data)
    print(f"Proportion of values above threshold {threshold}: {proportion_above_threshold:.2f}")
    ```

### 3. Object-Oriented Programming in Python
**Question:** Define a Python class and explain how it differs from a function.
- **Python Code:**
    ```python
    class GeneExpressionAnalyzer:
        def __init__(self, expressions, threshold=4):
            self.expressions = expressions
            this.threshold = threshold

        def calculate_proportion_above_threshold(self):
            count_above = sum(e > this.threshold for e in this.expressions)
            total = len(this.expressions)
            return count_above / total if total > 0 else 0

    # Example usage
    expressions = [5.99, 4.72, 6.29, 8.04, 4.53, 4.53, 8.15, 6.53, 4.06, 6.08]
    analyzer = GeneExpressionAnalyzer(expressions)
    proportion = analyzer.calculate_proportion_above_threshold()
    print(f"Proportion above threshold: {proportion:.2f}")
    ```

### 4. Data Plotting in Python
**Question:** Create a histogram of gene expression values and discuss its distribution.
- **Python Code:**
    ```python
    import matplotlib.pyplot as plt

    # Data for histogram plot
    histogram_data = [19.47, 13.76, 20.83, 28.71, 12.89, 12.89, 29.21, 21.91, 10.77, 19.88, 10.83, 10.81, 17.18, -2.22,
                  -0.52, 9.94, 5.88, 17.83, 6.83, 2.29, 28.19, 12.97, 15.61, 2.18, 10.1, 16.0, 4.64, 18.38, 9.59, 12.37,
                  9.58, 31.67, 14.88, 5.48, 22.4, 4.01, 16.88, -2.64, 3.05, 16.77, 21.65, 16.54, 13.96, 12.29, 1.69, 8.52,
                  10.85, 24.51, 18.09, -0.87, 17.92, 11.53, 8.91, 20.51, 24.28, 23.38, 7.45, 12.22, 17.98, 23.78, 10.69,
                  13.33, 5.04, 4.23, 22.31, 27.21, 14.35, 24.03, 18.25, 9.19, 18.25, 28.84, 14.68, 29.08, -8.58, 22.4,
                  15.78, 12.31, 15.83, -2.89, 13.02, 18.21, 28.3, 10.34, 7.72, 10.48, 23.24, 17.96, 10.23, 19.62, 15.87,
                  23.72, 8.68, 12.05, 11.47, 1.83, 17.67, 17.35, 15.05, 12.89]

    # Creating the histogram
    plt.figure(figsize=(10, 6))
    plt.hist(histogram_data, bins=20, color='blue', alpha=0.7)
    plt.title('Histogram of Gene Expression Values')
    plt.xlabel('Expression Value')
    plt.ylabel('Frequency')
    plt.grid(True)
    plt.show()
    ```

## Conclusion
This README includes my solutions to the technical questions for my EDIT AI/ML application. Each piece of code is accompanied by a brief description of what it does, demonstrating my approach to solving these questions.
