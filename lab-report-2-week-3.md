Part 2

The failure-inducing input (the code of the test)
The symptom (the failing test output)
The bug (the code fix needed)
Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?

This is the original reversed method from the arrayExamples class. 

![array](original%20reversed.png)

We can see that the intention is returning a NEW array but in reversed order. 

I tested this with an array of size 1, size 2, and size 3, all with different non-zero inputs. These all resulted in failure-inducing inputs:


