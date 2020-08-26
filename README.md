# Matrix Calculator
  
There are minor bugs need to be fixed:  
- [3,2] + [3,2] -> Invalid syntax  (Weird)
- [3,2] - [3,2] -> [3,2]  
  
## Description
  
Be similar to a simple calculator. In the problem, you’re asked to write a yacc program for a
matrix expression compiler. The objective of this problem contents two part. The first part is
to build a AST for the input expression. The second part is to check if the dimension on both
side of each operator is valid.
  
For example of multiplication: A 1×2 B 2×1 is valid which will generate a matrix with 1 x 1
dimension. But A 2×3 B 2×4 is invalid.
  
But if we take transpose of A in expression: A T 2×3 B 2×4 which equals to A 3×2 B 2×4 the whole
expression can be valid. The following are supported operators in this compiler:

addition `+`,   
subtraction `-`  
multiplication `*`  
transpose `^T`,  
parenthesis `( )`  

All matrix are 2-dimensional matrices which are represented as [column number , row number]
and matrix.column number and row number should be positive interger.e.g. [2, 3] is a 2x3
matrix.Your output should show “Syntax Error” if the input expression does not follow the
grammar. If it follows the grammar, then apply semantic check to see if the dimension on both
side of each operator is correct. Print “Semantic error on col ” followed by the location of the
first operator which makes the semantic error occur in post order of AST and add a new line.
If no any syntax error or semantic error, just print the column and row of the matrix.

***You will get zero points if you use c or c++ to solve this problem instead of lex and yacc.***

## Sample Data

| #   | Input                     | Output                   |
| --- | ------------------------- | ------------------------ |
| 1   | [2,1]^T*[2,1]             | 1 1                      |
| 2   | ([2,3]*[2, 3]^T)^T+[4,1]  | Semantic error on col 19 |
| 3   | [00000,123]+[0,123]       | Syntax Error             |
| 4   | [1,2]^T^T^T^T^T^T^T*[1,2] | 2 2                      |
