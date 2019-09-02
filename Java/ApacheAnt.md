## Java Build and Deployment Tool ##

1. Platform neutral and handle platform specific properties such as file seperators
2. Automating complicated repetitive tasks

## Build ##

1. Target is a collection of tasks to run as one unit. 
2. A deploy target may depend on package target and a package target can depend on compile target. 

## Data Type ##

1. Fileset represents a collection of files. It is used to include or exclude files that match certain pattern
2. Patternset is used to filter files based on pattern
3. Filelist is used tp filter files and does not support wildcard
4. Path is used to represente class path.

