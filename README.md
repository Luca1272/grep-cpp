Grep Remake in C++
This is a simplified implementation of the grep command-line utility in C++. The program matches patterns in input strings using regular expressions.
Features

Pattern matching at the beginning of a line
Full line pattern matching
Support for various regex patterns including:

Simple character matching
Wildcard (.)
Character classes ([abc], [^abc])
Quantifiers (+, ?)
Grouping and alternation ((a|b))
Backreferences (\1, \2, etc.)
Anchors (^, $)


Special character escapes (\d, \w)

Dependencies
This project uses standard C++ libraries and does not require any external dependencies.
Functions

find_char_at_same_level: Finds a character at the same nesting level in a pattern
decompose_pattern: Breaks down a regex pattern into smaller components
char_matches_pattern: Checks if a character matches a given pattern
save: Saves captured groups
match_pattern_at_beginning: Matches the pattern at the beginning of the input string
match_pattern: Matches pattern in the entire input line
main: The main function that handles input and output

Usage
The program takes two command-line arguments:

-E: Indicates that the next argument is a regular expression pattern
The regex pattern to match

sh./grep_remake -E "pattern"
The program then reads a line from standard input and attempts to match it against the given pattern.

Examples

Match a simple pattern:
sh
echo "Hello, World!" | ./grep_remake -E "Hello"

Match using a character class:
sh
echo "grep" | ./grep_remake -E "[a-z]rep"

Match using alternation:
sh
echo "cat" | ./grep_remake -E "c(a|o)t"

Match using quantifiers:
sh
echo "greeep" | ./grep_remake -E "gre+p"

Error Handling
The program includes basic error handling for invalid inputs and unhandled patterns. Error messages are output to standard error.
Future Improvements
This grep remake project has been a valuable exercise in implementing regex parsing and matching in C++. Potential areas for enhancement include:

Supporting more regex features (e.g., * quantifier, {n,m} repetition)
Improving performance for large input files
Adding options for case-insensitive matching
Implementing multi-line matching
Enhancing error messages and debugging output

Contributions and suggestions for improvements are welcome!
