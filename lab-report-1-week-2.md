# Lab Report 1 Week 2


## Installing Visual Studio Code

Go to [Visual Studio Code](https://code.visualstudio.com/) and install the IDE to begin logging in to a course specific account on ```ieng6```.


![](vscodess.png)


After installing VSCode, you can open the installation and it should automatically prompt you to begin coding.


![](vscodess2.png)


## Remotely Connecting

You will be able to find your course-specific account for CSE 15L [here](https://sdacs.ucsd.edu/~icc/index.php). The username for your account will begin with "cs15l", be followed by the quarter and year you are taking CSE 15L in, and end in three characters that are specific to you. This is what my page looks like:


![](etsss.png)


My username is **cs15lsp22ajy**. Your own course username will allow you to begin connecting remotely. Next, you should open a terminal in VSCode (a shortcut for this would be Ctrl + `) and type the following command. You should use your own username.

```$ ssh cs15lsp22ajy@ieng6.ucsd.edu```

You will be asked:

```Are you sure you want to continue connecting```

```(yes/no/[fingerprint])```


Type ```yes``` and press enter to contiue setting up your SSH connection.

At this point, you should be prompted to enter your password. Once you do, you are remotely connected!

## Trying Some Commands

Your terminal should look something like this:


![](terminalss.png)


At this point, you can start testing out command that will be useful to know. Good commands to start with would be ```cd```, ```ls```, ```pwd```, ```mkdir```, and ```cp```.

Testing out a command will look like this:

![](terminalss2.png)


As you can tell from the image above, the ```ls``` command will produce a list of files in the directory that you are currently in.

## Moving files with ```scp```

An important thing to note when setting up your ssh connection is that you are connecting to a computer that is outside your own. In our case, this is a computer in the CSE basement. When setting up a connection with a computer outside your own, your computer is refered to as the *client* and the outside computer as the *server*. When using a client and server, we use the ```scp``` command on the *client* terminal to transfer files between the accounts.

We can test this by creating a file on your computer called ```Username.java```

Paste this into the file you created:

```
class Username {
  public static void main(String[] args) {
    System.out.println(System.getProperty("user.name"));
  }
}
```

Once the file is saved, you can run it from your terminal to see what it outputs. do this by typing the following commands:

```
$ javac Username.java
$ java Username
```

You will see that the code displays the client username. After this, type the following ```scp``` command and log into your server account.

```
scp Username.java cs15lsp22ajy@ucsd.edu:~/
```

At this point, you should be able to log into the server account and use the ```ls``` command to see that ```Username.java``` is now in the directory. You can then run the previous ```javac``` and ```java``` commands to see that it now outputs the servers username instead. If you completed all of these steps right, your terminal shoud look somewhat like this:

![](terminalss3.png)

## Setting an SSH Key

## Optimize Remote Running
