# EDIT AI/ML TECHNICAL QUESTIONS FOR SKILLS DEVELOPMENT TRACK

## Overview
This document contains my responses to my EDIT AI/ML Internship application's technical questions. Below are my solutions to the provided problems, using Python and R.

## 4 Main Programming/Statistics Questions Responses

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
Question: Define a Python class and explain how it differs from a function.
    
What is a Python Class?
A Python class is a blueprint for creating objects. Classes provide a means of bundling data and functionality together. Creating a new class creates a new type of object, allowing new instances of that type to be made. Each class instance can have attributes attached to it for maintaining its state. Class instances can also have methods (defined by its class) for modifying its state.

How is this different from a function?
A function is a block of code which only runs when it is called. Data can be passed into a function as arguments and can return data as a result. A class, conversely, is a blueprint for creating objects (a particular data structure), providing initial values for state (member variables or attributes), and implementations of behavior (member functions or methods).

Examples of Classes:
1. `str` - A built-in Python class for representing string objects.
2. `list` - A built-in Python class for representing lists.
3. `dict` - A built-in Python class used to store data values in key:value pairs.

What are attributes and methods and how do they differ?
- **Attributes** are data stored inside a class or instance and represent the state or properties of the class or instance.
- **Methods** are functions defined inside a class body. They are used to define the behaviors of an object.

Example of a Class:
Here’s a simple example of a Python class:
```python
class Dog:
    # Class Attribute
    species = 'mammal'

    # Initializer / Instance Attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # instance method
    def description(self):
        return f"{self.name} is {self.age} years old"

    # instance method
    def speak(self, sound):
        return f"{self.name} says {sound}"
```
In this example, `Dog` class has a class attribute `species`, two instance attributes (`name` and `age`), and two methods `description()` and `speak()`.

Class for Proportion Calculation Challenge:
Now, let's turn the calculation of the proportion of genes that are highly expressed into a class:
```python
class GeneExpressionAnalyzer:
    def __init__(self, expressions, threshold=4):
        self.expressions = expressions
        self.threshold = threshold

    def calculate_proportion_above_threshold(self):
        count_above = sum(e > self.threshold for e in self.expressions)
        total = len(self.expressions)
        return count_above / total if total > 0 else 0

# Usage
expressions = [5.99, 4.72, 6.29, 8.04, 4.53, 4.53, 8.15, 6.53, 4.06, 6.08, ...]
analyzer = GeneExpressionAnalyzer(expressions, threshold=4)
proportion = analyzer.calculate_proportion_above_threshold()
print(f"Proportion above threshold: {proportion:.2f}")
```

This class, `GeneExpressionAnalyzer`, encapsulates the expressions and the threshold as instance attributes and provides a method to calculate the proportion of expressions that exceed the threshold. This object-oriented approach is advantageous for maintaining state and extending functionality in a modular way.

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

## My Brief Responses to 4 Bonus Technical Questions based on my hands-on experiences in my Inspirit AI and Veritas AI courses

a. Machine Learning
Machine learning is described as a subset of artificial intelligence that enables systems to learn from data and make decisions with minimal human intervention. The distinction is made between supervised learning, where models are trained on labeled data (e.g., spam detection in emails), and unsupervised learning, which involves learning from unlabeled data to identify patterns or structures (e.g., customer segmentation in marketing). Practical experience through coursework with Inspirit AI has enhanced understanding of real-world applications of these techniques.

b. Image Analysis
In automating the analysis of urine cells images, a computer program could be developed to emulate a pathologist's analysis using image processing techniques. This would involve segmenting the image into nuclei and cytoplasm and calculating the nucleus-to-cytoplasm ratio to assess potential malignancy. Foundational skills in image processing and analysis necessary for such biomedical imaging problems have been developed through training with Veritas AI.

c. Deep Learning/TensorFlow for Image Classification
Experiences with TensorFlow's playground, an interactive tool, have helped understand how neural networks can classify data based on visual patterns. Experiments with various network configurations to effectively classify shapes have demonstrated the importance of network architecture and parameter tuning. This hands-on experience has allowed exploration of the complexities of neural networks and their capabilities in pattern recognition.

d. Natural Language Processing
Using a neural network-based autocomplete tool has illustrated how neural networks can predict text sequences, significantly impacting how language and text are represented and processed by computer programs. The potential of tools like GPT-2 for applications in generating text and understanding language patterns has been highlighted. Coursework has provided practical context for these technologies, enhancing comprehension of NLP principles and their applications.

## Conclusion
This README includes my solutions/responses to the 4 main and 4 bonus technical questions for my EDIT AI/ML application. Each piece of code is accompanied by a brief description of what it does, demonstrating my approach to solving these questions.
