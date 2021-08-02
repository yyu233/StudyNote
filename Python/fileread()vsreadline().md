As noted above, f.read() reads the file as an individual string, and so allows relatively easy file-wide manipulations, such as a file-wide regex search or substitution.

f.readline() reads a single line of the file, allowing the user to parse a single line without necessarily reading the entire file. Using f.readline() also allows easier application of logic in reading the file than a complete line by line iteration, such as when a file changes format partway through.
