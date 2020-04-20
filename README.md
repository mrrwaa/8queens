# 8queens
 AI Task
Introduction
There are several ways to solve NP-hard problems. Genetic algorithm is one easy approach to solve such kind of problems. 
This article is about solving 8 queens puzzle with genetic algorithm using C#.
The eight queens puzzle is the problem of placing eight chess queens on an 8×8 chessboard so that no two queens attack each other.
Thus, a solution requires that no two queens share the same row, column, or diagonal.

In order to use genetic algorithm, it is a must to define the crossover operator, mutation operator, chromosome and genes.

Problem Representation
Gene: A gene is a number from 0 to 7 that means the row number that a queen is located. The position of the gene in a chromosome implies the column number of the queen. It is mandatory to locate one queen per column and row because there are same number of queens and columns/rows in the board.

Chromosome: A chromosome is a set of 8 genes. It is assumed to be that no duplicate genes in a chromosome.
Mutation: Mutation is done with swapping the gene that is to be mutated with a randomly selected gene (except the gene that is currently subjected to the mutation) from the same chromosome.

Crossover: Genes are drawn from the two parent chromosomes with the probability of 0.5. A gene is drawn from one parent and it is appended to the offspring chromosome. The corresponding gene is deleted in the other parent. This step is repeated until both parent chromosomes are empty and the offspring contains all genes involved.

Fitness Function: A collision is two queens who are able to attack each other. This means they are in the same diagonal, the same row or the same column. Since the chromosome has no duplicate genes and it guarantees that 2 queens are not in a single column it is only needed to calculate the diagonal collisions. Therefore maximum number of collisions that can occur is 28. The fitness function is a higher-is-better function, so calculate it by subtracting the amount of collisions that occur in the current state from 28. A solution would have 0 collisions and thus a fitness of 28.
Classes and Structures
class GeneticAlgo: The class that is responsible for all the operations of genetic algorithm.
class FitnessComparator: A comparator class to sort chromosomes with fitness value in order to show the final population in the table.
struct Chromosome: The structure that represents a chromosome which include genes, fitness and its cumulative of average fitness.
class MainFrame: The class that responsible for handling user interface and create initial population in order to pass to the genetic algorithm.
class Board: The class that is responsible for graphical view and operations of the chess board.
Variables
private const int <code>MAX_FIT = 28; holds the maximum fitness.
 
YouTube video link: https://youtu.be/QvdNLCEmpHE
