# Writing a Bash Script for Lab 7 (Lab Report 4)

**script.sh**
```
#!/bin/bash

git clone git@github.com:serrachow/lab7.git

cd lab7
ls
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

sed '43 s/index1/index2/' ListExamples.java > changed.java && mv changed.java ListExamples.java

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

git add ListExamples.java
git commit -m "fixed ListExamples.java"
git push origin main
```

**commands to input into the terminal**
```
ssh cs15lwi23xxx@ieng6.ucsd.edu
bash script.sh
```

This script would make running the code faster since you only have to type one command (besides the one logging into the host server). Here's a line-by-line breakdown for what each line in bash script does.

`#!/bin/bash`

The she-bang (`#!`) tells the system to send the script to a specific shell, in this case the Bash shell.

`git clone git@github.com:serrachow/lab7.git`

Clones the forked repository.

`cd lab7`

`ls`

Changes directory into the lab7 directory and prints out the list of files and directories in lab7

`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`

`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`

Runs the javac command to compile and runs the java -cp command to run the JUnit tests. It should show that the tests do not pass.

`sed '43 s/index1/index2/' ListExamples.java > changed.java && mv changed.java ListExamples.java`

This is actually two commands in one line. The first part, `sed '43s/index1/index2/' ListExamples.java > changed.java`, uses the sed command to change the index1 to index2 at line 43. The `s/` stands for substitution. The sed command sends the changes to a new file called `changed.java` instead of printing to standard output. The two commands are concatenated with `&&`. The second part, `mv changed.java ListExamples.java`, moves the contents of `changed.java` back to `ListExamples.java`.
