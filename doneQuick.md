# CSE Labs - Done Quick !

1. Log into ineg6

`ssh cs15lwi23acx@ieng6.ucsd.edu<enter>`

Using the `ssh` command, we can secure an encrypted connection between two hosts. Because we generated SSH keys, there is no need to type in a password when logging in. Now we are entering commands from the ieng6 host server, not our local server. 

![image](https://user-images.githubusercontent.com/105563729/221442861-4fd85e15-edac-4c84-a657-1b79c254861f.png)

2. Clone your fork of the repository from your Github account

`git clone git@github.com:serrachow/lab7.git<enter>`

Because we have an SSH key used to authenticate Github, we can use the SSH url to clone the forked Github repository. Because our account has access, this will help in cloning and pushing future changes to the repository. The `git clone` command makes a copy of the repository into our account on the ieng6 server.

![image](https://user-images.githubusercontent.com/105563729/221443194-4ffc921f-d178-40fd-b0d7-25ebb0cc3bfa.png)

3. Run the tests, demonstrating that they fail

`cd lab7<enter>`

`ls<enter>`

`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java<enter>`

`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests<enter>`

`cat ListExamplesTests.java<enter>`

First we use `cd lab7` to change the directory we're in into the lab7 directory. Then we use the command `ls` to make sure that `ListExamples.java` and `ListExamplesTest.java` are inside the lab7 directory. We run `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`to compile and run the JUnit tests. From the screenshot, we can tell that `testMerge2` in `ListExamplesTests` failed. If we use `cat ListExamplesTests.java` to see inside the tester file, we can see that we must fix the merge method.

![image](https://user-images.githubusercontent.com/105563729/221443431-4b8894d9-659c-49a3-8038-68101287ef07.png)

![image](https://user-images.githubusercontent.com/105563729/221443566-9d3bde6f-6b70-4c0c-90e6-85ce8a6acfbb.png)

4. Edit the code file to fix the failing test


5. Run the tests, demonstrating that they now succeed


6. Commit and push the resulting change to your Github account
