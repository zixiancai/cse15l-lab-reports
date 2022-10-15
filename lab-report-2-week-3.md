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

All of these errors were similar to this:

```
arrays first differed at element [0]; expected:<3> but was:<0>
```

By closely examining the code, we can see that this method is creating a "newArray",assigns all the values of our original array to the values of this new array, and returns the orginal but modified array. Instead, we should be assigning values to the new array via the values of our original. Then returning our new, temporary array.


This is how I did it:
![reverse changed](changed%20reverse.png)

(The second for loop was my way of outputing the array for testing)

This was the result:
![the result of array changes](the%20result%20of%20array%20changes.png)