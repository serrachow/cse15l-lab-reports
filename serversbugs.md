# StringServer

**StringServer code:**

![image](https://user-images.githubusercontent.com/105563729/215361441-db0b546c-4b46-437b-aea2-08a14ddba865.png)

**Add Message**

![image](https://user-images.githubusercontent.com/105563729/215361948-aab9a671-15a9-4867-992a-38a2743e8da1.png)
![image](https://user-images.githubusercontent.com/105563729/215361976-4ca2b31e-3cbf-4acb-a98c-9fb85144969e.png)
![image](https://user-images.githubusercontent.com/105563729/215362055-57896579-44b2-479e-8d50-5a3f81c1dcde.png)

The methods called in my code is handleRequest, which checks the path of the URL and takes in two parameters. handleRequest checks that the path is either `"/"`, which prints out all the Strings that have been added, or `"/add-message"`. When adding a message, the code checks that `parameters[0] = "s"` and that `"parameters[1]" = <inputString>"`. Ever inputString is added to startingString, which is later printed out separated by `"\n"` for a new line. 

# Bugs

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
