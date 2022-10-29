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

![image](https://user-images.githubusercontent.com/86514102/198816185-ccd6714c-221f-498b-8d0d-0697119f6015.png)

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

