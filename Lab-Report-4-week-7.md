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
















