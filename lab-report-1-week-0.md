Hey future self! This is you from the past reminding you what you did for this lab assignment. Also, Hi future students

Your first actual task (excluding all the boring introductions) was to install VScode and Github. Two things that should've already been downloaded to start this lab.

Here are the links:

[github link](https://desktop.github.com/)

[vscode link](https://code.visualstudio.com/)


![1](vscode(labreport).png)

Next up, you needed to test the waters via remotely connecting. Using simple commands like ls and ssh on the remote server.

![2](simple%20commands.png)

![3](testing%20ls.png)

Sadly, you encountered some problems here at Part 6, when you needded to access SSH with scp

Even though you couldn't finish this during the lab session you were able to access your password the day after. I think the password issue was a common occurence and might have been the result of server overload. However, you got it done! Here are your results

![4](moving%20files%20ssh%20via%20scp.png)

You now have access to the remote computer and server. Now you are easily able to do things like playing with a java file even though you don't have java installed. 

This is the main part of the assignment, using ssh keys so you don't have to log in via your password everytime you want to do anything. Take note of "ssh-keygen". It is essentially a public key for you to be autenticated with the remote server. In this context, this can be done via ssh like this: "ssh cs15lfa22XX@ieng6.ucsd.edu".  This is how you generate it, storing it involves your home directory and quite a few commands written in the lab.

You would replace XX with your specific username given by the link above, try it yourself!

![5](ssh%20keys.png)

Here is the code in text for "WhereAmI.java" Take a look!:

```<code>class WhereAmI {

  public static void main(String[] args) {

    System.out.println(System.getProperty("os.name"));

    System.out.println(System.getProperty("user.name"));

    System.out.println(System.getProperty("user.home"));

    System.out.println(System.getProperty("user.dir"));`

  }
  
}
<code>
```



Lastly, what I believed to be the main idea of this lab. The ability to extrapolate the time we save via not needing to enter a password over the course of many iterations. This was summed up with the idea of "optimizing remote running"

![6](optimizing%20remote%20running.png)

