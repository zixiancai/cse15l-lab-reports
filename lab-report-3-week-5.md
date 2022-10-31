Starting off with the "less" command. By default, the less command outputs a file's contents and allows you to navigate through the file very much like a webpage. 
Where you can scroll via the arrow keys in terminal. Here is a example of the default:

![image](https://user-images.githubusercontent.com/86514102/199015335-dc96e0c2-b798-4565-94e4-816ef67a0247.png)


A simple yet useful command to add to the command line would be -N, 

![image](https://user-images.githubusercontent.com/86514102/199020743-82dd5c5f-1219-4735-a771-951104ec53cc.png)

This command simply adds line numbers into the file contents

![image](https://user-images.githubusercontent.com/86514102/199020920-e432a661-18f7-43ce-897c-1ecc4f1200d9.png)


![image](https://user-images.githubusercontent.com/86514102/199020959-9d46431b-a2d4-4331-b535-dd7a616e3234.png)

This command, although simple, is quite practical and useful. It can pave the way for other commands that require line numbers or just allows you to keep 
better track of your code. This is most prevalent in very long text files where there might even be 1000 lines, -N solves the issue of line numbers easily.


Another relatively useful command is the "Ignore Case" when it comes to searching:

![image](https://user-images.githubusercontent.com/86514102/199023147-7c35c0a5-ba0d-4763-9996-1e338099d064.png)

![image](https://user-images.githubusercontent.com/86514102/199024299-59411a26-c273-42e1-af96-962a8ae3e4f4.png)

This, without the ignore case command, will produce:

![image](https://user-images.githubusercontent.com/86514102/199024341-86782dda-1d32-4499-8a63-0882be8cb68a.png)

However, when we add the command, "-I", we get this message:

![image](https://user-images.githubusercontent.com/86514102/199024469-edb62ba4-49a4-4df9-adbb-7b5c35464709.png)

And immediately following this with a search yields:

![image](https://user-images.githubusercontent.com/86514102/199024957-48eb644f-78f2-455b-91b0-922483fd3b48.png)


![image](https://user-images.githubusercontent.com/86514102/199024645-cc851f7c-02b8-4dab-8f5a-f70c33bfa80a.png)

This command is useful because sometimes you just want to search something where case doesn't matter. One might assume that the file doesn't contain the item that they 
wanted to search if they choose to simply search for the exact item or word. Using this command along with your search can provide some insurance that there
really does or does not exist a certain string in your file. 


For my third command, I chose the -F command because I thought it was just intresting:

![image](https://user-images.githubusercontent.com/86514102/199030205-737c8e95-044c-42a1-b525-59b8c4a20dce.png)


![image](https://user-images.githubusercontent.com/86514102/199030158-c9777f2c-c06f-4934-ae0d-fa8250dad860.png)

This command just quits the less command after it produces its output. I believe this is meant to be a substiute to just printing out the text of a file. 
A good use for this command that I can think off involves "pipes". A tool that allows you to use multiple commands at once. Via this, you would be able to
maybe do some work with less, add a few arguments, making some tweaks or changes, and then just exiting after all these commands are done. This might be a way to
make something more efficent or less time-consuming.















For the "find" command. By default, it just searches for files in a directory

For the first command line options I found intresting it would be this:

![image](https://user-images.githubusercontent.com/86514102/199008990-bae45393-ecf3-48d3-bdcd-093f614e8cf4.png)

Here is the link if you want to see for yourself!: "https://man7.org/linux/man-pages/man1/find.1.html"

I found this command line option particularly intresting because the idea of that code can be efficent has appeared quite a few times during my CS journey so far. 
What peaked my intrest was this particular arguement: 

![image](https://user-images.githubusercontent.com/86514102/199009519-c921dece-bdcd-48e6-b3fd-2ff3e9d312dd.png)

Here are my 3 screenshots:

![image](https://user-images.githubusercontent.com/86514102/199013666-e1d89d57-5e4c-4ef2-862c-f5127392b8fa.png)

![image](https://user-images.githubusercontent.com/86514102/199014564-6663bf92-3547-42cb-8994-9d1bf881eef3.png)

![image](https://user-images.githubusercontent.com/86514102/199014737-7ecb3660-83a2-4bd8-b5db-190bbd7c1ca8.png)




I found this intriguing because I enjoyed the lectures about Big-O Notation and improving the efficency of your code in my prior CS classes. This command line option 
improves the optimization of the find method. In doing so, it often will speed up the process of the search and theoretically yield a faster result. This is particularly useful
in large files where searching can take a long time even for a fast computer. Or maybe where we need to find a file over many, many directories. Speeding up this process
via efficent and fast algorithims can save us potentially hours or even days. However, in our context we can't really see the speed of this command.