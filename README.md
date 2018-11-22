# Optimal Key Splitting Schemas

### What is it?
Mnemonic code key splitting is a secure method for splitting a mnemonic code across several word lists with redundancy in case one or more lists is compromised. Mnemonic codes are commonly used to recover cryptocurrency wallets.

### What is an optimal schema?
The optimal key splitting schema for a pattern is the schema where each list contains the least number of words possible to fit the pattern. If you were splitting 12 words across two lists, having 11 words on each list isn't optimal. To score a schema, sum 2<sup>words on list</sup> for all lists. The optimal schema will have the lowest score.

### The Trivial Example
The most basic example is non-redundant key splitting. With this key splitting schema, you separate your list of words into separate lists with no words repeated across lists. If any of the lists are lost the word list can not be reconstructed. 

Example word list: rapid foam

|        | List 1 | List 2 |
|--------|--------|--------|
| Word 1 | rapid  |        |
| Word 2 |        | foam  |

### Three Lists, Need Two
This redundant key splitting schema splits the mnemonic code into three lists where two of the lists are required to reconstruct the full list. This schema can be generalized for any word list with a length divisible by three, and will be optimal.

Example word list: buffalo spoil fall

|        | List 1  | List 2  | List 3 |
|--------|---------|---------|--------|
| Word 1 | buffalo | buffalo |        |
| Word 2 | spoil   |         | spoil  |
| Word 3 |         | fall    | fall   |


Six word example: cake twice awesome please scheme you

|          | List 1         | List 2     | List 3         |
|----------|----------------|------------|----------------|
| Word 1-2 | cake twice     | cake twice |                |
| Word 3-4 | awesome please |            | awesome please |
| Word 5-6 |                | scheme you | scheme you     |

### Four Lists, Need Three
This schema splits the mnemonic code into four lists where three of the lists are required to reconstruct the full list. This schema can be generalized for any word list with a length divisible by six, and will be the optimal for that list.

Example word list: atom armor dwarf caught drum success

|        | List 1 | List 2 | List 3  | List 4  |
|--------|--------|--------|---------|---------|
| Word 1 | atom   | atom   |         |         |
| Word 2 | armor  |        | armor   |         |
| Word 3 |        | dwarf  | dwarf   |         |
| Word 4 | caught |        |         | caught  |
| Word 5 |        | drum   |         | drum    |
| Word 6 |        |        | success | success |

### Five Lists, Need Three
Still searching for the optimal schema. Feel free to contribute. The above examples were found through a complete search of possible combinations with a parallelized python script, this approach does not scale well for larger list collections, currently researching alternative schema generation methods.
