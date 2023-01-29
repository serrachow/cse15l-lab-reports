# StringServer

**StringServer code:**

![image](https://user-images.githubusercontent.com/105563729/215361441-db0b546c-4b46-437b-aea2-08a14ddba865.png)

**add message**

![image](https://user-images.githubusercontent.com/105563729/215361948-aab9a671-15a9-4867-992a-38a2743e8da1.png)
![image](https://user-images.githubusercontent.com/105563729/215361976-4ca2b31e-3cbf-4acb-a98c-9fb85144969e.png)
![image](https://user-images.githubusercontent.com/105563729/215362055-57896579-44b2-479e-8d50-5a3f81c1dcde.png)

The methods called in my code is handleRequest, which checks the path of the URL and takes in two parameters. handleRequest checks that the path is either `"/"`, which prints out all the Strings that have been added, or `"/add-message"`. When adding a message, the code checks that `parameters[0] = "s"` and that `"parameters[1]" = <inputString>"`. Ever inputString is added to startingString, which is later printed out separated by `"\n"` for a new line. 
