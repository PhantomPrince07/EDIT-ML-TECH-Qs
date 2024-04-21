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

    gene_expressions = [19.47, 13.76, 20.83, 28.71, 12.89, 12.89, 29.21, 21.91, 10.77, 19.88]
    plt.hist(gene_expressions, bins=10, color='blue', alpha=0.7)
    plt.title('Histogram of Gene Expression Values')
    plt.xlabel('Expression Value')
    plt.ylabel('Frequency')
    plt.show()
    ```

## Conclusion
This README includes my solutions to the technical questions for my EDIT AI/ML application. Each piece of code is accompanied by a brief description of what it does, demonstrating my approach to solving these questions.
