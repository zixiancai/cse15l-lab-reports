Grade.sh in Code Block:

```
CPATH=".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar"

rm -rf student-submission

mkdir student-submission

git clone $1 student-submission

cp TestListExamples.java student-submission

cd student-submission


if [[ -f "ListExamples.java" ]]
    then 
        echo "Found ListExamples.java, +1 Point (1/1)"
    else
        echo "Cannot find ListExamples.java, Grade: 0/5"
        exit 0
fi 

javac -cp $CPATH *.java

if [[ $? -eq 0 ]]
    then 
        echo "No Compilation Error! Good Job, +1 Point (2/2)"
    else 
        echo "Compilation Error! Grade: 1/2" 
        exit 0
fi 

java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > outputFile.txt

if [[ $? -eq 0 ]]
    then
        cat outputFile.txt
        echo "Tests Passed! Good Job, +2 Points (4/4)"
        exit
    else 
        cat outputFile.txt
        echo "Tests Failed! Grade: 2/4"
        exit
fi
```

For Line Numbers:

![image](https://user-images.githubusercontent.com/86514102/204331705-a436094f-d008-42ab-9e1d-f3c20643d6b2.png)


Screenshots:

The Link from Week 7: https://github.com/ucsd-cse15l-f22/list-methods-corrected

Image:

![image](https://user-images.githubusercontent.com/86514102/204325456-1927c592-c39b-46b5-b7f3-933471c6ab66.png)

Got "near to full credit" as expected

Link: https://github.com/ucsd-cse15l-f22/list-methods-compile-error

Image:

![image](https://user-images.githubusercontent.com/86514102/204325627-cfc9c65d-1645-415c-af4d-9976a0aeb917.png)

Exposed the "semicolon error" as expected.

Link: https://github.com/ucsd-cse15l-f22/list-methods-filename

Image:

![image](https://user-images.githubusercontent.com/86514102/204326266-ceec0e7e-63b6-4c2c-8c1b-ce9f8c96f639.png)

Wrong final name results in the first part of grade.sh failing, a score of 0/4, as expected.


Tracing of grade.sh:

I will be choosing this example:

![image](https://user-images.githubusercontent.com/86514102/204330481-3e2a21f7-1a02-4f8d-a7e8-253949b0333e.png)


Line 1:

```CPATH=".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar"```

What this did was create a variable called CPATH that is simply copies the required snippet to run JUnit from week3. I also had a few errors with my OS being windows
and looking at Piazza posts I solved a few of my issues with this.

-Standard Output: Nothing 

-Standard Error: Nothing

-Return Code: 0

The next line with a command (line 3) contains this:

```rm -rf student-submission```

This is just to remove, recursively, a "student-submission" file/directory that already exists...if there was one. This is good measure because we don't want 
previously submitted student submissions to replace the grade of all the subsequent ones.

-Standard Output: Nothing 

-Standard Error: Nothing

-Return Code: 0

Next is line 5:

```mkdir student-submission```

This just creates a new directory. This will be useful later because we want to move TestListExamples.java into this new directory. 

-Standard Output: Nothing 

-Standard Error: Nothing

-Return Code: 0

Next, line 7:

```git clone $1 student-submission```

Cloning what is in the arguement into student-submission.

-  Standard Output: Nothing 

-  Standard Error: Nothing

-  Return Code: 0

Next, line 9:

```cp TestListExamples.java student-submission```

Copying TestListExamples.java into student submission.

Standard Output: Nothing 

Standard Error: Nothing

Return Code: 0

Line 11:

```cd student-submission```

Changing the directory to "student-submission"

Standard Output: Nothing 

Standard Error: Nothing

Return Code: 0

Next is the if statement:

(Lines 14-20)

```if [[ -f "ListExamples.java" ]]
    then 
        echo "Found ListExamples.java, +1 Point (1/1)"
    else
        echo "Cannot find ListExamples.java, Grade: 0/5"
        exit 0
fi 
```

This esentially asks if "ListExamples.java" can be found with "-f". In this repository, it can be found and subsequently
the echo statement is then released, echoing "Found ListExamples.java..."
Since everything else before the fi is bound by the else statement, the lines 18 and 19 did not run.

Summing this up:
Lines 14-17 and 20 ran, this is because the if statement was true, there can be a "ListExamples.java" found inside of the current directory.
Also, all of the lines that ran didn't have any standard output, error, and of course their return code was 0.

Line 22: 

```javac -cp $CPATH *.java```

Now that we tested and grade for the existence of ListExamples.java, we need to compile javac. This will also spot out any compilation errors and provide a return code
that we will be using.

Standard Output: Nothing 

Standard Error: Nothing

Return Code: 0

Lines 24-30:

```if [[ $? -eq 0 ]]
    then 
        echo "No Compilation Error! Good Job, +1 Point (2/2)"
    else 
        echo "Compilation Error! Grade: 1/2" 
        exit 0
fi 
```
Since our return code for our previous statement was "0", this if statement holds true. Therefore, lines 24-26 and 30 will run.
As a result, 28-30 will not run. 

Also, for this code snippet, the standard

