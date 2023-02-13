# Part 1: StringServer

**StringServer code:**

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String startingString = " ";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return startingString;
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    startingString = startingString + "\n" + parameters[1];
                    return startingString;
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

**Add Message**

![image](https://user-images.githubusercontent.com/105563729/215361948-aab9a671-15a9-4867-992a-38a2743e8da1.png)
![image](https://user-images.githubusercontent.com/105563729/215361976-4ca2b31e-3cbf-4acb-a98c-9fb85144969e.png)
![image](https://user-images.githubusercontent.com/105563729/215362055-57896579-44b2-479e-8d50-5a3f81c1dcde.png)

The methods called in my code is handleRequest, which checks the path of the URL and takes in two parameters. handleRequest checks that the path is either `"/"`, which prints out all the Strings that have been added, or `"/add-message"`. When adding a message, the code checks that `parameters[0] = "s"` and that `"parameters[1]" = <inputString>"`. Ever inputString is added to startingString, which is later printed out separated by `"\n"` for a new line. 

# Part 2: Bugs

**Failure-inducing Input**
```
@Test
  public void testReverseInPlace2() {
    int[] input1 = {1, 2, 3, 4, 5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{5, 4, 3, 2, 1}, input1);
  }
 ```
 **Result**
 
 ![image](https://user-images.githubusercontent.com/105563729/215363282-84d7ce3c-8a11-4dd7-a293-3416849942c6.png)

**Input that does not induce a Failure**

```
@Test 
  public void testReverseInPlace() {
    int[] input1 = { 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1);
  }
 ```
**Result**
 
![image](https://user-images.githubusercontent.com/105563729/215363436-05603cee-dc55-4350-ab7d-6f17b4feb216.png)

**Symptom**

![image](https://user-images.githubusercontent.com/105563729/215363502-a0e14dda-a56d-4fff-bfe1-9d1b360f788a.png)

**Before**

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
 ```
 
**After**

```
  static void reverseInPlace(int[] arr) {
    int[] tempArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      tempArray[i] = arr[i];
    }
    for (int i = 0; i < arr.length; i++) {
      arr[i] = tempArray[arr.length - i - 1];
    }
  }
```

A temporary new array is needed in order to properly reverse in place as the function is drawing from the very array that it reversed. 

# Part 3: What I Learned

I learned how to launch a local server and how you can change the URL inputs using different parameters and printing results out using String format.
