# Ternary Spec
Ideas for a mixed binary/ternary ALU implemented on a FPGA
## Unary operations
| NUMBER | OPERATOR | OUTPUT: 0 1 |
| --- | --- | --- |
| 0 | FALSE    | 0 0 |
| 0 | IDENTITY | 0 1 |
| 0 | NEGATION | 1 0 |
| 0 | TRUE     | 1 1 |
## Binary operations
| OPERATOR | INPUT A | INPUT B | OUTPUT | - |
| --- | --- | --- | --- | --- |
| AND | A | B | AB | 0 0 0 1 |
| NAND | A | B | ~( AB ) | 1 1 1 0 |
| OR  | A | B | A+B | 0 1 1 1 |
| NOR  | A | B | ~( A+B ) | 1 0 0 0 |
| XOR  | A | B | A^B | 0 1 1 0 |
| XNOR  | A | B | ~( A^B ) | 1 0 0 1 |

## Unary operations
| NUMBER | OPERATOR | OUTPUT: - 0 + | CATEGORY |
| ---: | --- | --- | --- |
| 0 | Always Negative   | - - - |
| 1 | -                 | - - 0 |
| 2 | Is Positive       | - - + | COMPARE |
| 3 | -                 | - 0 - |
| 4 | Clamp to Zero or Negative | - 0 0 | CLAMP |
| 5 | Identity          | - 0 + | BUFFER |
| 6 | Is Zero           | - + - | COMPARE |
| 7 | -                 | - + 0 |
| 8 | Is Zero or Positive       | - + + | COMPARE |
| 9 | -                 | 0 - - |
| 10 | -                | 0 - 0 |
| 11 | -                | 0 - + |
| 12 | -                | 0 0 - |
| 13 | Always Zero      | 0 0 0 |
| 14 | Clamp to Zero or Positive | 0 0 + | CLAMP |
| 15 | Increment        | 0 + - | SUM
| 16 | -                | 0 + 0 |
| 17 | -                | 0 + + |
| 18 | Is Negative      | + - - | COMPARE |
| 19 | Decrement        | + - 0 | SUM
| 20 | Is Negative or Positive  | + - + | COMPARE |
| 21 | Negation         | + 0 - | INVERT |
| 22 | -                | + 0 0 |
| 23 | Absolute         | + 0 + | SUM
| 24 | Is Negative or Zero      | + + - | COMPARE |
| 25 | -                | + + 0 |
| 26 | Always Positive  | + + + |
