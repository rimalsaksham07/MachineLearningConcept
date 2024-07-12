
# Genetic Algorithm to Solve 4 $𝑥^2$−25=0
# Overview
This program uses a genetic algorithm to find an approximate solution to the equation 4 $𝑥^2$−25=0 .The algorithm encodes potential solutions as binary strings, evaluates their fitness based on the given equation, and iteratively evolves the population of solutions through crossover operations.

# Structure
The program consists of the following key components:
# Encoding and Decoding Functions
encode(x): Converts a floating-point number to a 12-bit binary string.

decode(binary): Converts a 12-bit binary string back to a floating-point number.

Crossover Function
crossover(parent1, parent2): Performs a single-point crossover between two parent binary strings to produce two offspring.

Genetic Algorithm Function
genetic_algorithm(): Runs the genetic algorithm to find the solution to the equation.

# Installation (Jupyter)
To run this project locally,follow these steps:

1. **Clone the repository:**

   ```sh
   git clone https://github.com/rimalsaksham07/Genetic_Algorithm-.git


2. **Install Jupyter Notebook and dependencies:**
 Install Jupyter Notebook and other dependencies using pip.
```
pip install jupyter
```

3.**Start Jupyter Notebook:**
Launch Jupyter Notebook to run the genetic algorithm notebook.
```
jupyter notebook
```

4.**Open the notebook:**
Navigate to the GeneticAlgorithm.ipynb file in your Jupyter Notebook interface and open it to execute the genetic algorithm code.

5.**Run the genetic algorithm:**
Follow the procedure within the notebook to view results.

6.**Shutdown Jupyter Notebook:**
Once finished, you can shut down Jupyter Notebook by pressing Ctrl + C in the terminal where it's running and confirming the shutdown.


# Encoding Function
The encode function converts a number x to a 12-bit binary string. The conversion involves multiplying 𝑥 by 64 and formatting the result as a binary string:


```python
  def encode(x):
      """Convert a number to binary string."""
       return format(int(x * 64), '012b')
```
# Decoding Function
The decode function converts a 12-bit binary string back to a floating-point number by interpreting the binary string as an integer and dividing by 64:
```python
def decode(binary):
    """Convert a binary string to a number."""
    return int(binary, 2) / 64
```
# Crossover Function
The crossover function performs a single-point crossover between two parent binary strings. A random crossover point is chosen, and the binary strings are split and recombined to form two new offspring:

```python
def crossover(parent1, parent2):
    """Perform two-point crossover between parents."""
    point = random.randint(1, len(parent1) - 1)
    child1 = parent1[:point] + parent2[point:]
    child2 = parent2[:point] + parent1[point:]
    return child1, child2

```
# Genetic Algorithm Function
he genetic_algorithm function initializes a population of random binary strings, then iteratively evolves the population over a specified number of generations. The fitness of each individual is calculated based on the absolute value of the equation 4 $𝑥^2 $−25 = 0 , Individuals with better fitness are more likely to be selected as parents. New offspring are created through crossover and replace the old population. The best solution found is returned at the end:

```python
def genetic_algorithm():
    """Run a simple genetic algorithm to find solution for 4 $x^2$ - 25 = 0."""
    population = [''.join(random.choice('01') for _ in range(12)) for _ in range(10)]
    
    for _ in range(50):  # Number of generations
        # Calculate fitness (lower is better)
        fitness = [abs(4 * decode(ind)**2 - 25) for ind in population]
        
        # Select parents
        parents = random.choices(population, weights=[1/f for f in fitness], k=10)
        
        # Create new population through crossover
        new_population = []
        for i in range(0, 10, 2):
            child1, child2 = crossover(parents[i], parents[i+1])
            new_population.extend([child1, child2])
        
        population = new_population
    
    # Find best solution
    best = min(population, key=lambda ind: abs(4 * decode(ind)**2 - 25))
    return decode(best)

result = genetic_algorithm()
print(f"Approximate solution: {result}")
print(f"F({result}) = {4 * result**2 - 25}")
```
 # Usage
Run the script to execute the genetic algorithm and print the approximate solution and its evaluation:

# Bash
```bash
python genetic_algorithm.py
```
The output will be an approximate solution to the equation 
4 $𝑥^2$−25=0 and the evaluation of the equation at that solution.

# Dependencies
The program requires Python 3.6 or higher.



# Genetic Algorithm to Solve 4 $𝑥^2$−25=0
# Overview
This program uses a genetic algorithm to find an approximate solution to the equation 4 $𝑥^2$−25=0 .The algorithm encodes potential solutions as binary strings, evaluates their fitness based on the given equation, and iteratively evolves the population of solutions through crossover operations.

# Structure
The program consists of the following key components:
# Encoding and Decoding Functions
encode(x): Converts a floating-point number to a 12-bit binary string.

decode(binary): Converts a 12-bit binary string back to a floating-point number.

Crossover Function
crossover(parent1, parent2): Performs a single-point crossover between two parent binary strings to produce two offspring.

Genetic Algorithm Function
genetic_algorithm(): Runs the genetic algorithm to find the solution to the equation.

# Installation (Jupyter)
To run this project locally,follow these steps:

1. **Clone the repository:**

   ```sh
   git clone https://github.com/rimalsaksham07/Genetic_Algorithm-.git


2. **Install Jupyter Notebook and dependencies:**
 Install Jupyter Notebook and other dependencies using pip.
```
pip install jupyter
```

3.**Start Jupyter Notebook:**
Launch Jupyter Notebook to run the genetic algorithm notebook.
```
jupyter notebook
```

4.**Open the notebook:**
Navigate to the GeneticAlgorithm.ipynb file in your Jupyter Notebook interface and open it to execute the genetic algorithm code.

5.**Run the genetic algorithm:**
Follow the procedure within the notebook to view results.

6.**Shutdown Jupyter Notebook:**
Once finished, you can shut down Jupyter Notebook by pressing Ctrl + C in the terminal where it's running and confirming the shutdown.


# Encoding Function
The encode function converts a number x to a 12-bit binary string. The conversion involves multiplying 𝑥 by 64 and formatting the result as a binary string:


```python
  def encode(x):
      """Convert a number to binary string."""
       return format(int(x * 64), '012b')
```
# Decoding Function
The decode function converts a 12-bit binary string back to a floating-point number by interpreting the binary string as an integer and dividing by 64:
```python
def decode(binary):
    """Convert a binary string to a number."""
    return int(binary, 2) / 64
```
# Crossover Function
The crossover function performs a single-point crossover between two parent binary strings. A random crossover point is chosen, and the binary strings are split and recombined to form two new offspring:

```python
def crossover(parent1, parent2):
    """Perform two-point crossover between parents."""
    point = random.randint(1, len(parent1) - 1)
    child1 = parent1[:point] + parent2[point:]
    child2 = parent2[:point] + parent1[point:]
    return child1, child2

```
# Genetic Algorithm Function
he genetic_algorithm function initializes a population of random binary strings, then iteratively evolves the population over a specified number of generations. The fitness of each individual is calculated based on the absolute value of the equation 4 $𝑥^2 $−25 = 0 , Individuals with better fitness are more likely to be selected as parents. New offspring are created through crossover and replace the old population. The best solution found is returned at the end:

```python
def genetic_algorithm():
    """Run a simple genetic algorithm to find solution for 4 $x^2$ - 25 = 0."""
    population = [''.join(random.choice('01') for _ in range(12)) for _ in range(10)]
    
    for _ in range(50):  # Number of generations
        # Calculate fitness (lower is better)
        fitness = [abs(4 * decode(ind)**2 - 25) for ind in population]
        
        # Select parents
        parents = random.choices(population, weights=[1/f for f in fitness], k=10)
        
        # Create new population through crossover
        new_population = []
        for i in range(0, 10, 2):
            child1, child2 = crossover(parents[i], parents[i+1])
            new_population.extend([child1, child2])
        
        population = new_population
    
    # Find best solution
    best = min(population, key=lambda ind: abs(4 * decode(ind)**2 - 25))
    return decode(best)

result = genetic_algorithm()
print(f"Approximate solution: {result}")
print(f"F({result}) = {4 * result**2 - 25}")
```
 # Usage
Run the script to execute the genetic algorithm and print the approximate solution and its evaluation:

# Bash
```bash
python genetic_algorithm.py
```
The output will be an approximate solution to the equation 
4 $𝑥^2$−25=0 and the evaluation of the equation at that solution.

# Dependencies
The program requires Python 3.6 or higher.


