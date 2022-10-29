Part 1

The following is my code for SearchEngine.java:

```java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int counter = 0;
    String word[] = new String[99];  
    String words = "";
    String searcher;
    String matches = "";


    public String handleRequest(URI url) {
        
        if (url.getPath().equals("/")) {
            return ("You need to enter a word");
        } 
        else {
            //System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    word[counter] = (parameters[1]);
                    counter++;
                    words = words + " " + word[counter-1];
                    return ("You have added the word: " + word[counter-1]);
                
            }
        }
            if(url.getPath().contains("/display")){
                return words;
            }

            if(url.getPath().contains("/search")){
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    searcher = (parameters[1]);
                }
                for(int i=0; i<counter; i++){
                    if(word[i].contains(searcher)){
                        matches = matches + " " + word[i];
                    }
                }
                return ("Displaying all the words with the word: " + searcher + " \n" + matches);
            }

            return "404 Not Found!";
        }
    }
}

class SearchEngine {
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

The following are my screenshots for the required assignments:
This is me starting the server!:

![image](https://user-images.githubusercontent.com/86514102/198816185-ccd6714c-221f-498b-8d0d-0697119f6015.png)

This is what follow when you click the "link", 

![image](https://user-images.githubusercontent.com/86514102/198816226-994aec12-04f1-47d6-b3d8-5fb8220391c8.png)

Here are a few examples of using the "add method":

![image](https://user-images.githubusercontent.com/86514102/198816301-be83bc18-a835-463a-a2dc-160c5149fbd2.png)

![image](https://user-images.githubusercontent.com/86514102/198816306-9ce3c39b-c28f-490a-b2a0-0b637f17ea37.png)

![image](https://user-images.githubusercontent.com/86514102/198816319-70850953-8431-4045-800e-9ac4b1f87cf7.png)

For these three screenshots, the methods in this block of code are being called: 
```java
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    word[counter] = (parameters[1]);
                    counter++;
                    words = words + " " + word[counter-1];
                    return ("You have added the word: " + word[counter-1]);
                
            }
```

The "relevant values of the argument" are strings that get added to this array:
```java
    String word[] = new String[99];  
```

When it comes to the class, these strings are just being managed by all the code here...:

![image](https://user-images.githubusercontent.com/86514102/198816462-6cc2798f-1cdb-4f6a-a799-090bb7254014.png)

... All of these are just variables keeping track of the index of the array, the word itself, and are being used for other methods like "display" and /search. 
But in the context of just the add method, we just need to think about the first two. What this means is that the purpose of this add method is to add values into our word array, but in the backend of things the words are being stored for other purposes (other methods). If these values change, the method will just add even more strings into our array. This is completely indedpendent of all the values prior.

The next screenshot is how I use the query, "search". 
First, this is the code:
```java
            if(url.getPath().contains("/search")){
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    searcher = (parameters[1]);
                }
                for(int i=0; i<counter; i++){
                    if(word[i].contains(searcher)){
                        matches = matches + " " + word[i];
                    }
                }
                return ("Displaying all the words with the word: " + searcher + " \n" + matches);
            }
```
The screenshot:

![image](https://user-images.githubusercontent.com/86514102/198816604-6eb21a62-1ae5-43f8-bfd6-276dd697e7dc.png)

This method uses the string "matches" than has been tracking the strings used via add, and now searches through it via the .contains method.
The relevant arguments are strings that you wish to look up that have been added via the add function. When it comes to relevant arguements in the class, the strings are all that are releveant. As they are being kept track of via the array, but they are actually independent of the other methods inside the class. If these values change it will operate just like a search method would, searching instead for a new string rather than the old. 

I also added a method called display, as I believe that is particular useful when it comes to keeping track of the array.

![image](https://user-images.githubusercontent.com/86514102/198816744-12ba0e7f-b3bf-47d7-9a58-47209762de49.png)

This is self-explanatory, the call to this method just displays all the values in the array. New instances or calls to this method are independent of the ones prior, simply displaying with is currently in the "words" array.



Part 2

The failure-inducing input (the code of the test)
The symptom (the failing test output)
The bug (the code fix needed)
Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?

This is the original reversed method from the arrayExamples class. 

![array](original%20reversed.png)

We can see that the intention is returning a NEW array but in reversed order. 

I tested this with an array of size 1, size 2, and size 3, all with different non-zero inputs. These all resulted in failure-inducing inputs:

![errors](three%20errors.png)

The symptoms or these errors were similar to this:

```
arrays first differed at element [0]; expected:<3> but was:<0>
```

By closely examining the code, we can see that this method is creating a "newArray",assigns all the values of our original array to the values of this new array, and returns the orginal but modified array. This is our bug and its connection to the symptom.

Instead, we should be assigning values to the new array via the values of our original. Then returning our new, temporary array.



This is how I did it:
![reverse changed](changed%20reverse.png)

(The second for loop was my way of outputing the array for testing)

This was the result:
![the result of array changes](the%20result%20of%20array%20changes.png)



Second Error:

The failure-inducing input (the code of the test)
The symptom (the failing test output)
The bug (the code fix needed)
Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?


I don't think I can do this without some extra help, I'm encountering error after error. I feel familiar with LinkedLists and Lists but am having a hard time with all the errors in creating a test. This is what I have so far:

![image](https://user-images.githubusercontent.com/86514102/198818340-4da1a729-c45a-4f15-95f1-de0b740b6ab1.png)
