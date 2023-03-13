# Writing a Bash Script for Lab 7 (Lab Report 4)

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
