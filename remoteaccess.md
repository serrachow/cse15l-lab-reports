# Remote Access

This is a tutorial on how to log into a course-specific account on `ieng6` for future CSE 15L students.

---

## Step 1: Installing Visual Studio Code

You can either find a computer that already has Visual Studio Code installed or install it on your own computer.

[Visual Studio Code Website](https://code.visualstudio.com/)

When it is installed, the window opened should look something similar to this: (Windows)

![image](https://user-images.githubusercontent.com/105563729/211946977-3a3f4c1a-543b-4bf5-857e-a643ed0391c4.png)

## Step 2: Remotely Connecting

If you're on Windows, we need to install `git` for Windows. 

[Git for Windows](https://gitforwindows.org/)

To open the terminal, use Ctrl + `.

From the dropdown menu, choose to use Git Bash.

![image](https://user-images.githubusercontent.com/105563729/211947883-70d773eb-986a-4bf9-a141-00edc4410594.png)

To use the `ssh` command, first type in your account username followed by `@ieng6.ucsd.edu`.

```
$ ssh cs15lw23acx@ieng6.ucsd.edu
```

Since this is the first time you are connecting to the server, the terminal will ask `Are you sure you want to continue connecting (yes/no/[fingerprint])? `; type `yes`.

Next time in your password. Your password will not show up due to security reasons.

The result should be something similar to this:

![Screenshot_20230111_033806](https://user-images.githubusercontent.com/105563729/211948466-64726e2d-b149-421a-85c1-4e5ff6064ce2.png)

## Step 3: Trying Some Commands

Try `pwd`.

The result should be the path to your account.

Try `mkdir hello` and `pwd`.

Then try `ls`

You should see `hello` under your list of directories.

Lastly try `cd ..`

The result should show your parent folder.

Results of these commands:

![Screenshot_20230111_034424](https://user-images.githubusercontent.com/105563729/211948818-c8904539-e97d-4008-be42-68165c1c65da.png)
