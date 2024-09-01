# Grep Remake in C++

This project is a simplified implementation of the `grep` command-line utility in C++. It allows for pattern matching in input strings using regular expressions.

## Features

### Pattern Matching:
- **Beginning of Line:** Matches patterns at the start of a line.
- **Full Line:** Matches patterns across the entire line.

### Regex Patterns Supported:
- **Simple Character Matching:** Match specific characters.
- **Wildcard (`.`):** Matches any single character.
- **Character Classes (`[abc]`, `[^abc]`):** Matches characters within or outside specified sets.
- **Quantifiers (`+`, `?`):** Specify the number of occurrences.
- **Grouping and Alternation (`(a|b)`):** Matches either of the grouped patterns.
- **Backreferences (`\1`, `\2`, etc.):** Matches the text previously matched by capturing groups.
- **Anchors (`^`, `$`):** Matches the start or end of a line.
- **Special Character Escapes (`\d`, `\w`):** Matches digits or word characters.

## Dependencies
This project uses standard C++ libraries and does not require any external dependencies.

## Functions
- **`find_char_at_same_level`:** Finds a character at the same nesting level in a pattern.
- **`decompose_pattern`:** Breaks down a regex pattern into smaller components.
- **`char_matches_pattern`:** Checks if a character matches a given pattern.
- **`save`:** Saves captured groups.
- **`match_pattern_at_beginning`:** Matches the pattern at the beginning of the input string.
- **`match_pattern`:** Matches the pattern in the entire input line.
- **`main`:** Handles input and output.

## Usage
The program takes two command-line arguments:
- **`-E`:** Indicates that the next argument is a regular expression pattern.
- **Regex Pattern:** The pattern to match.

### Example Usage:
```sh
./grep_remake -E "pattern"
The program reads a line from standard input and attempts to match it against the given pattern.

Examples
Match a Simple Pattern:
sh

echo "Hello, World!" | ./grep_remake -E "Hello"
Match Using a Character Class:
sh

echo "grep" | ./grep_remake -E "[a-z]rep"
Match Using Alternation:
sh

echo "cat" | ./grep_remake -E "c(a|o)t"
Match Using Quantifiers:
sh

echo "greeep" | ./grep_remake -E "gre+p"
Error Handling
The program includes basic error handling for invalid inputs and unhandled patterns. Error messages are output to standard error.

Future Improvements
This project serves as a foundation for implementing regex parsing and matching in C++. Potential enhancements include:

Supporting more regex features (e.g., * quantifier, {n,m} repetition).
Improving performance for large input files.
Adding options for case-insensitive matching.
Implementing multi-line matching.
Enhancing error messages and debugging output.
Contributions and suggestions for improvements are welcome!
