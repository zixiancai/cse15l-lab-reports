Edit:
I read the assignment incorrectly and did 3 different options for 3 different commands. I don't want to erase anything so I will just add two more examples for each of the "grep" command options, for a total of 3 grep commands that have 3 different examples.

Starting off with the "less" command. By default, the less command outputs a file's contents and allows you to navigate through the file very much like a webpage. 
Where you can scroll via the arrow keys in terminal. Here is a example of the default:

![image](https://user-images.githubusercontent.com/86514102/199015335-dc96e0c2-b798-4565-94e4-816ef67a0247.png)


A simple yet useful command to add to the command line would be -N, 

```less -N 911report```

![image](https://user-images.githubusercontent.com/86514102/199020743-82dd5c5f-1219-4735-a771-951104ec53cc.png)

This command simply adds line numbers into the file contents

![image](https://user-images.githubusercontent.com/86514102/199020920-e432a661-18f7-43ce-897c-1ecc4f1200d9.png)


![image](https://user-images.githubusercontent.com/86514102/199020959-9d46431b-a2d4-4331-b535-dd7a616e3234.png)

This command, although simple, is quite practical and useful. It can pave the way for other commands that require line numbers or just allows you to keep 
better track of your code. This is most prevalent in very long text files where there might even be 1000 lines, -N solves the issue of line numbers easily.


Another relatively useful command is the "Ignore Case" when it comes to searching:

```less -I 911report``` -> ```/CHAPTER```

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

```less -F 911report```

![image](https://user-images.githubusercontent.com/86514102/199030205-737c8e95-044c-42a1-b525-59b8c4a20dce.png)


![image](https://user-images.githubusercontent.com/86514102/199030158-c9777f2c-c06f-4934-ae0d-fa8250dad860.png)

This command just quits the less command after it produces its output. I believe this is meant to be a substiute to just printing out the text of a file. 
A good use for this command that I can think off involves "pipes". A tool that allows you to use multiple commands at once. Via this, you would be able to
maybe do some work with less, add a few arguments, making some tweaks or changes, and then just exiting after all these commands are done. This might be a way to
make something more efficent or less time-consuming.















For the "find" command. By default, it just searches for files in a directory

For the first command line options something I found intresting would be this:

```find -O3 911report```

![image](https://user-images.githubusercontent.com/86514102/199008990-bae45393-ecf3-48d3-bdcd-093f614e8cf4.png)

Here is the link if you want to see for yourself!: "https://man7.org/linux/man-pages/man1/find.1.html"

I found this command line option particularly intresting because the idea of that code can be efficent has appeared quite a few times during my CS journey so far. 
What peaked my intrest was this particular argument: 

![image](https://user-images.githubusercontent.com/86514102/199009519-c921dece-bdcd-48e6-b3fd-2ff3e9d312dd.png)

Here are some examples even though this doesn't change any output:

![image](https://user-images.githubusercontent.com/86514102/199013666-e1d89d57-5e4c-4ef2-862c-f5127392b8fa.png)

![image](https://user-images.githubusercontent.com/86514102/199014564-6663bf92-3547-42cb-8994-9d1bf881eef3.png)

![image](https://user-images.githubusercontent.com/86514102/199014737-7ecb3660-83a2-4bd8-b5db-190bbd7c1ca8.png)




I found this intriguing because I enjoyed the lectures about Big-O Notation and improving the efficency of your code in my prior CS classes. This command line option 
improves the optimization of the find method. In doing so, it often will speed up the process of the search and theoretically yield a faster result. This is particularly useful
in large files where searching can take a long time even for a fast computer. Or maybe where we need to find a file over many, many directories. Speeding up this process
via efficent and fast algorithims can save us potentially hours or even days. However, in our context we can't really see the speed of this command.


Another command I found useful was this:

```find -size 50b```

This command has a manual here:

![image](https://user-images.githubusercontent.com/86514102/199042822-53e127a4-a0b1-4ac0-a625-42a53daeec10.png)


![image](https://user-images.githubusercontent.com/86514102/199042798-cefe243c-d660-457e-b5f3-c2e2fe7d7f2c.png)

This command essentially finds all the files and directories with a size smaller than the given parameter. In this case, we are trying to find all the files and directories of size 50 bytes or less. This can be particularly useful when you have multiple copies of the same file in terms of strings or words or any other data structure. But because you want to have the "lightest" one, you are able to pick and choose via this -size command.


For the last find command, I found "used" to be quite useful.
```find 911report -used 1```

I think many of us take a break and forget all about the things we did the day prior. "-used" is an amazing command that combats this. Here is what it does!:

![image](https://user-images.githubusercontent.com/86514102/199045921-ab4491bb-ed1a-4b1a-8093-ff33688526b1.png)

And this is what it produced:

![image](https://user-images.githubusercontent.com/86514102/199046092-ac7338f3-e524-4ab7-8b84-946446da36bd.png)

Because I have accessed or made changes to all of these files they show up. But in the situation where I'm not actively using these pages for more than a day, the "used" command will not show these files. But changing the argument to 3 or 4 would make them show up if I was AFK for 3 or 4 days. This command is useful because you can easily pick back up where you started even though you were doing something else!





Finally we have grep, a command that searches for specific patterns in individual files.

A very notable command to add to the command line of grep would be -c:

![image](https://user-images.githubusercontent.com/86514102/199048319-505c3906-ec91-4924-94dc-7c6cca35e353.png)

A command like this:
```grep -c planes */chapter1.txt```

Will produce:

![image](https://user-images.githubusercontent.com/86514102/199048488-2682ff04-e8c0-4f7b-b315-37cdebdd0346.png)

instead of the messy default of the entire file, which just highlights every instance of a word. 
I believe this command is useful because sometimes you just want the number of times a word appears in a file, not where and when. Maybe you have a essay and you feel like you use a certain word too many times. This command would be quite perfect, as all you need to determine if you use a word too much is the number of times you use it.

Here is another example of this but with multiple files:

```grep -c "Background" biomed/*.txt```

![image](https://user-images.githubusercontent.com/86514102/201457429-d8fe3725-cc4e-4d36-9713-54ec10d15d86.png)

This is a example of me using grep -c to search for a "Background" string in all the text files inside of biomed. This is particularly useful say if you have suspicions of a word being used too many times when it comes to multiple files. Take a example like student submitted texts such as essays. Maybe a third grade class is turning in text files that contain too many instances of the word "Trichotillomania", or "Tergiversation", or any big word that shouldn't be in there vocabulary. 

My last example of grep -c would be:

```grep -c " " biomed/*.txt```

![image](https://user-images.githubusercontent.com/86514102/201457756-32a73fa8-3fba-4839-8bfd-8b74ca435364.png)

Even though grep is meant to be used to search for patterns, you can tweak it using -c to search for words or characters like you would with word count. By putting in " " as a arguement you can see how many whitespaces are in a .txt file. This might help you find the word count and allow you to detect if there are any blank spaces students used to fill up their essay.


Another useful grep command would be:

![image](https://user-images.githubusercontent.com/86514102/199049128-3f7ec363-6a3b-4fc7-82ea-edaad0881a9f.png)

An example of me using it:

```grep -L Osama */chapter-3.txt```

![image](https://user-images.githubusercontent.com/86514102/199049386-15ee5276-9a4d-41d3-af6c-485335e8aa1d.png)

This command, "-L", prints the names of the files that DON'T have a specific pattern. This could be particularly useful when it comes to looking up the same word in a stack of papers/files. The first thing that comes to mind might be something like a essay checker for teachers. If there is a phrase that is sus for a student to be saying, they could use this command to pull all the "papers" or text documents that have and don't this phrase. 

Another example would be this:

```grep -L "TEXAS" 911report/chapter-7.txt```
```grep -L "CALIFORNIA" 911report/chapter-7.txt```

![image](https://user-images.githubusercontent.com/86514102/201457939-3bb54698-1db0-437f-afbd-69325ffd5221.png)


The chapter-7.txt file talks about the "First arrivals in California". Say I was tired of hearing about papers on Texas and wanted to hear about anything about California. I would use grep -L to test if a file was about Texas. And since we saw chapter 7 pop up, it doesn't contain the string "Texas". And if I use the same command but on "California" it will display nothing, showing that the file indeed was talking about California.

For my final example of grep -L:

```grep-L "1999" 911report/*.txt```
```grep-L "1990" 911report/*.txt.txt```

![image](https://user-images.githubusercontent.com/86514102/201458047-84317bb8-ed43-4777-9390-ccd60d8ad2bf.png)

I decided to use a year as my input string. This can be particularly useful for sorting a journal or folder with multiple text files chronologically. We can see that documents that don't contain the year "1999" and "1990" pop up. Therefore, we can use this information to put them somewhere before or after the other text files in this folder.

I chose this for my third grep command:

![image](https://user-images.githubusercontent.com/86514102/201461282-579ad07a-b0f3-4a3b-8abb-35030f256224.png)

```grep "world" 911report/chapter-13.1.txt```
```grep -i "world" 911report/chapter-13.1.txt```

```grep "WORLD" 911report/chapter-13.1.txt```
```grep -i "WORLD" 911report/chapter-13.1.txt```

```grep "World" 911report/chapter-13.1.txt```
```grep -i "world" 911report/chapter-13.1.txt```

This is another in line command that allows the command to ignore the cases. This is quite important because in the context of searching patterns via grep, you really don't want to have the case get in the way of your search. This example shows how grep doesn't search for all the strings "world" without -i, as some are "World" like in "World War". This is important because words can have different meanings depending on their case.

![image](https://user-images.githubusercontent.com/86514102/201461509-60f2d9ba-2a75-4eed-a4a7-3f42bec51215.png)
![image](https://user-images.githubusercontent.com/86514102/201461524-e41f9e68-e55c-41e7-a021-438a8c07c378.png)


Another example of -i:

```grep "WAR" 911report/chapter-13.1.txt```

```grep -i "WAR" 911report/chapter-13.1.txt```

![image](https://user-images.githubusercontent.com/86514102/201461627-e964ce2c-84a9-4e20-a0d0-5feabe1e3c14.png)

Sometimes cases can completely change the output. By using -i, we can actually confirm that our command works as intended. The default command of "grep" doesn't do this, making this quite important when doing multiple searches through various documents.

Third example of -i:

```grep "america" 911report/chapter-13.1.txt```
```grep -i "america" 911report/chapter-13.1.txt```
Grep searching can be used to spot all the errors in a text file. And -i can be specifically used to spot the misspelling of countries or names, as their first letter should be capitilized. If you were forced to use grep to solve a problem in a text file, -i could be the solution to searching for un-capatilized letters to countries or names. 

![image](https://user-images.githubusercontent.com/86514102/201461784-ecd49ad8-24ab-47d0-9284-d342a2c3e7f2.png)

In this particular example, we have confirmed using -i, that there truly are no "america"'s in the text file. And by looking through the output, we can also confirm that their only exists "America"'s capatilized.




This is a fourth command for grep:

![image](https://user-images.githubusercontent.com/86514102/199050517-5e5a2f3f-1bec-4384-84ca-6822e4043279.png)

```grep --quiet Usama */chapter-3.txt```


![image](https://user-images.githubusercontent.com/86514102/199050750-d9d353f0-f3d9-4549-8af9-4625dd7dcfa2.png)

This command does not write anything, exits if there actually is a pattern found, and exits in the case of an error. It is hard to think about why exactly you would want something like this command line in your grep command. The only thing I can think of is if you are passing this command as a argument for another. What this means is that if you were to combine grep with find or some other command, the output might be too convoluted or messy. Blocking the output so it displays nothing no matter what, is a good alternative to having a messy output. 








