Resubmission contains the entirety of part 2, I didn't double check that the GitHub page took a while to load after I made the edit.

Part 1:

This is what one of my lab partners did:

"Changing the name of the start parameter and its uses to base"
or
"In DocSearchServer.java, change the name of the start parameter of getFiles, and all of its uses, to instead be called base.":


```vim DocSearchServer.java<Enter>```

![image](https://user-images.githubusercontent.com/86514102/201652751-fb33c668-fa9c-4da5-8808-3995703fda4a.png)

This is just me opening via vim.

After opening the file we will have our "cursor" at the beginning of the file:

![image](https://user-images.githubusercontent.com/86514102/201653207-8d7ab0fb-4bcf-4142-9e91-39915a17ae40.png)

Next, since we want to search for the occurences of "start" we should use the "/" command to search. Doing this:

```/star``` 

(Without even pressing Enter)

...will result in this:

![image](https://user-images.githubusercontent.com/86514102/201653537-ce0c5c81-1e94-40c8-b273-43d4c2bf7cfc.png)

We will then have to press enter in order to do our next command:

```<Enter>```

We now want to replace the word with the command "ce", and immediately after we type: "base".
This will replace the current word with "base", so in this case we are replacing this instance of start with base.

```cebase```

These are the screenshots for this change:

Before "ce":

![image](https://user-images.githubusercontent.com/86514102/201654801-88c2ec06-c7b1-4314-b45b-334ea8243ff7.png)

After "ce":

![image](https://user-images.githubusercontent.com/86514102/201654983-ba82b8be-f383-4a8d-96a4-463caade761c.png)

Typing "base":

![image](https://user-images.githubusercontent.com/86514102/201654718-aa965129-faa9-4715-a5d0-b49c7a94a734.png)

We have sucessfully made the change but we want to do this series of commands multiple times to change all the instances of start to base.
The "." command allows us to repeat the command before, and the "n" command allows us to repeat the previous search but for the next position of the cursor. 
So what we should do now is escape insert mode with "Esc" and do "n" followed by "." until we have changed all the instances.

Here is that in code:

```<Esc>```

The image of me escaping insert mode:
![image](https://user-images.githubusercontent.com/86514102/201656912-4849259e-c8bb-4637-aeb6-f683efb64e36.png)

Just pressing "n" will search for the next 'start':

```n```

Here is the screenshot of this:

![image](https://user-images.githubusercontent.com/86514102/201656000-bdcee1e2-504d-4982-89b4-fb274699007a.png)

Now we want to use "." to repeat the same command, the command "cebase" which changes/replaces the current word into base:

```.```

This is the screenshot:

![image](https://user-images.githubusercontent.com/86514102/201656143-23001386-2837-4aee-bfad-86e426367db8.png)

We repeat these commands until we are done with all instances of start, replacing them with base.
First we search with "n", then repeat the "cebase" command with ".":

```n.```

This is the screenshot of "n":

![image](https://user-images.githubusercontent.com/86514102/201657628-61a1b956-ebc3-4a75-9cd0-a35ac48c1613.png)

Then ".":

![image](https://user-images.githubusercontent.com/86514102/201657657-0f8665cd-bfe0-4a86-a4c8-4f55716a1e6e.png)

Then repeating this again for other instances of start:

```n.```

Another screenshot of "n":

![image](https://user-images.githubusercontent.com/86514102/201657758-92b7e3c0-3eea-4263-a105-c4e7dae7d6a5.png)

Another screenshot of ".":

![image](https://user-images.githubusercontent.com/86514102/201657808-aefa5df2-1f17-4755-b89d-18fbb2bc08fa.png)

Because we are finished replacing all instances of start to base, we are done.

So we should save and quit with ":wq"

```:wq<Enter>```

This is the screenshot:

![image](https://user-images.githubusercontent.com/86514102/201657955-e58c2892-0415-4853-82ac-535456373101.png)



So to sum up this is the entire string of commands we used:

```vim DocSearchServer.java<Enter>```

Then: 

```/star<Enter>cebase<Esc>n.n.n.:wq!```

Part 2:

Me manually making the change:

![image](https://user-images.githubusercontent.com/86514102/201667115-62f12262-ec2e-4bb9-9207-f8c745391ea8.png)

Scp:

![image](https://user-images.githubusercontent.com/86514102/201664011-50201c8b-6a42-4ad4-8ddf-f4890e11ed7d.png)

Ssh:

![image](https://user-images.githubusercontent.com/86514102/201664115-1a4f3227-cfa7-4db0-88e0-4e7b903f2412.png)

Bash:

![image](https://user-images.githubusercontent.com/86514102/201667770-0dcb385d-a922-4a8e-86d7-1c1bc1adfdd7.png)

![image](https://user-images.githubusercontent.com/86514102/201667881-3b622e89-d3b6-4ec0-9b1c-bdcf4ae8d0a9.png)

This took a total of ~7 minutes. Including the 4-5 minutes of scp, recursively copying the files.


Using vim:

(Just repeating the task from part 1)


```vim DocSearchServer.java<Enter>```

```/star<Enter>cebase<Esc>n.n.n.:wq!```

![image](https://user-images.githubusercontent.com/86514102/201669735-c7b5a95e-5e52-4d8e-8ced-8f610d63e32a.png)


This totaled to roughly 3 minutes. Not much difficulties in general, just annoying that I have to wait for scp.


Questions:
Which of these two styles would you prefer using if you had to work on a program that you were running remotely, and why?

If I had to work on a program remotely I would actually choose making the changes locally then scp'ing it. This is because a code editor like VScode allows me to see the changes, make changes to it instantly, and compile/test it instantly. Whereas remotely, I have to use something like vim, albeit quite efficent and useful, which honestly might cause more problems than it helps. Also, I believe you have to be extra careful with the remote server because it is very much like a final draft as you are uploading permanent changes to the server. Where as locally, you might be able to test it like it were a "rough draft".


What about the project or task might factor into your decision one way or another? (If nothing would affect your decision, say so and why!)


If the project or task simply involved typing and fixing a few syntax errors, I would defnitely choose to use something like vim remotely to make changes. However, for large projects that require a train of though or maybe peer review. I have to choose local changes and uploading it to the remote server. This is because people can easily look at your code, make changes, and test your code before uploading it to an offical database or server. This also brings up the topic of security and how important it is to have a secure live server. Maybe in the context of a bank, a data breach might be easily possible because of the errors you uploaded to the cloud. By testing the changes locally, this brings more benefits to situations like this.


















