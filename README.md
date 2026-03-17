# Logical Expression Evaluator (Tautology Checker)

#1.Project Overview

This project implements a structural parser and evaluator for propositional logic expressions. The program analyzes a user-input logical formula and determines its universal truth value across all possible variable assignments. Specifically, it classifies the input expression into one of three categories:

Tautology (重言式): The expression evaluates to True for all possible variable assignments.

Contradiction (矛盾式): The expression evaluates to False for all possible variable assignments.

Satisfiable (可满足式): The expression is True for some assignments and False for others.

#2.Data Structure & Architecture
1. Abstract Data Type: Binary Tree (BiTree)
The logical expression is mapped into a hierarchical tree structure, which naturally represents the precedence and nested nature of logical operations.

2. Auxiliary Stacks (C++ STL)
To construct the binary tree from a raw string input, the program utilizes the C++ Standard Template Library (std::stack). It implements a bottom-up expression parsing algorithm (similar to the Shunting-yard algorithm) using two stacks:

Operator Stack (OPS): Holds logical operators and parentheses.

Operand/Node Stack (ODS): Holds constructed tree nodes (variables or sub-trees).

#3.Core Algorithms
Input Validation & Parsing (isLegal, GetNumberOfVariety): First, the program scans the string to ensure valid syntax and extracts the number of unique variables present in the expression.

Tree Construction (CreateLogisticBinaryTree): Using the two stacks, the program reads the string character by character. When an operation needs to be resolved based on precedence rules, it pops operators and operands, links them as parent and children nodes, and pushes the resulting sub-tree back onto the operand stack.

Recursive Evaluation (JudgePatern): Once the tree is built, the program systematically assigns all possible True/False combinations to the variables. For each combination, it evaluates the tree recursively from the leaves to the root.

#4.Environment & Setup
Language: C++

Standard Library: Uses C++ STL (<stack>, <string>, <iostream>).

Compiler: Standard C++ compiler (e.g., GCC, Clang, MSVC).

The core architecture relies on a Logical Binary Tree combined with auxiliary Stacks to parse and evaluate the expressions.
