# Epistemic Programming Practices

## Table of contents

<ul>
  <li><a href="#error-types">1. Error Types</a>
    <ul>
      <li><a href="#testing-and-errors">1.1. Testing and Errors</a></li>
      <li><a href="#command-line-errors">1.2. Command line errors</a></li>
      <li><a href="#syntactical-errors">1.3. Syntactical errors</a></li>
      <li><a href="#runtime-errors">1.4. Runtime errors</a></li>
    </ul>
  </li>
  <li><a href="#debugging">2. Debugging</a>
    <ul>
      <li><a href="#categorize-debugging-activities">2.1. Categorize Debugging Activities</a></li>
      <li><a href="#debugging-command-line-errors">2.2. Debugging Command-Line Errors</a></li>
      <li><a href="#activity-debug-command-line-errors">2.3. Activity: Debug Command-Line Errors</a></li>
      <li><a href="#debugging-compile-errors">2.4. Debugging Compile Errors</a></li>
      <li><a href="#activity-debug-compile-errors">2.5. Activity: Debug Compile Errors</a></li>
    </ul>
  </li>
  <li><a href="#design">3. Design</a>
    <ul>
      <li><a href="#steps-for-solving-a-programming-problem">3.1. Steps for solving a programming problem</a></li>
      <li><a href="#dissecting-a-programming-problem">3.2. Dissecting a programming problem</a></li>
      <li>Example: <a href="#dissecting-a-programming-problem-example">Dissecting a programming problem example</a></li>
      <li><a href="#develop-a-plan-to-solve-the-problem">3.3. Develop a plan to solve the problem</a></li>
      <li>Example: <a href="#develop-a-plan-to-solve-the-problem-example">Develop a plan to solve the problem example</a></li>
      <li><a href="#identifying-appropriate-constructs">3.4. Identifying appropriate constructs.</a></li>
      <li>Example: <a href="#identifying-appropriate-constructs-example">Identifying appropriate constructs example</a></li>
      <li><a href="#write-code">3.5. Write code</a></li>
      <li><a href="#testing-and-debugging-logical-errors">3.6. Testing and Debugging Logical errors</a></li>
    </ul>
  </li>
  <li><a href="#reference">4. Reference</a>
    <ul>
      <li><a href="#identifying-what-you-need-from-reference-material">4.1. Identifying What You Need from Reference Material</a></li>
      <li><a href="#define-a-technical-term">4.2. Define a Technical Term</a></li>
      <li><a href="#clarify-command-usage">4.3. Clarify Command Usage</a></li>
      <li><a href="#clarify-syntax">4.4. Clarify Syntax</a></li>
      <li><a href="#discover-tool">4.5. Discover Tool</a></li>
      <li><a href="#ask-a-question">4.6. Ask a Question</a></li>
    </ul>
  </li>
  <li><a href="#testing">5. Testing</a>
    <ul>
      <li><a href="#the-need-for-testing">5.1. The Need for Testing</a></li>
      <li><a href="#black-box-testing">5.2. Black-Box Testing</a></li>
      <li><a href="#test-flowchart">5.3. Test Flowchart</a></li>
      <li><a href="#debug-logic-error-flowchart">5.4. Debug Logic Error Flowchart</a></li>
      <li><a href="#bisection-debugging">5.5. Bisection Debugging</a></li>
    </ul>
  </li>
</ul>

<a id="error-types"></a>

# 1. Error Types

Learning objectives:

After successfully completing this section, students will be able to:

- Distinguish shell command, syntactical, and logical errors.
- Debug shell command errors.
- Debug and fix syntactical errors.
- Debug and fix logical errors.

<a id="testing-and-errors"></a>

## 1.1. Testing and Errors

We want programs that are predictable, robust, and secure. Programs are predictable when they behave the way we want them to behave. You wouldn't want an email application that sends your emails to the wrong person. Programs are robust when they don't unexpectedly crash. Imagine writing a 20-page document, and your word processing application crashes, and you lose everything that you wrote! Programs are secure when all private information remains private. These days, there is a lot of news about data breaches and hacking. We want to make programs that keep our data and our users' data safe.

How do we ensure that our programs are predictable, robust, and secure? We need to thoroughly test our programs before sharing them. In our case, we will follow some steps to test our Hello World program.

Let's recall the process for writing, compiling, and executing our program.

1. Write source code.
2. Save the source code to a file.
3. Locate the file.
4. Verify the existence of the file.
5. Compile the file.
6. Run the file.

There are three common errors you might encounter while following the process. Therefore, when you encounter an error, we will use the following process to identify the error to guide how we might fix it.

1. Check whether it is a command-line error. We see these errors anywhere from step 3 to step 6
2. Check whether it is a syntactical error. We see these errors in step 5.
3. Check whether it is a logical error. We see these errors in step 6.

<a id="command-line-errors"></a>

## 1.2. Command line errors

Many people find errors and automatically assume there is something wrong with their source code. However, the issue might actually be related to the command line.

### Location and existence

The list shows errors you might encounter related to the location and existence of your source code or executable code. We offer some suggestions for fixing these errors.

|Command|Error message|Explanation|Fix|
|---|---|---|---|
|clang++ hello.cc -o hello|clang: error: no such file or directory: 'hello.cc'<br>clang: error: no input files|The compiler cannot find the file called hello.cc in the current location.|Make sure you save the file in the correct location.Make sure you navigate to the folder that contains the file.Make sure you write the name of the source code file correctly.|
|./hello|bash: no such file or directory: ./hello|We assume that after we compiled the file without errors, the compilation produces the executable file. In this case, the system cannot find the executable file called hello.|Make sure you navigate to the folder that contains the executable file.Make sure you write the name of the executable file correctly.Make sure there were no compilation errors because they will not produce an executable file.|

### Compilation commands

The list shows errors you might encounter related to the compilation command. We offer some suggestions for fixing these errors.

|Command|Error message|Description|Fix|
|---|---|---|---|
|clang+ hello.cc -o hello|bash: command not found: clang+|The name of the compiler is clang++.|Make sure your spelling is correct.|
|clang++ -o hello|clang: error: no input files|The compiler needs you to provide the filename of your source code.|Provide the source code file name.|

### Execution commands

The list shows errors you might encounter related to the compilation command. We offer some suggestions for fixing these errors.

|Command|Error message|Description|Fix|
|---|---|---|---|
|hello|bash: command not found: hello|This is not the correct way to run a program on Linux|Don't forget to type ./ before the name of the executable file|

<a id="syntactical-errors"></a>

## 1.3. Syntactical errors

The C++ programming language is quite complex so minor mistakes can generate sometimes intimidating errors. Errors related to the source code are called syntactical errors. We will not cover all syntactical errors in C++ as there are too many. However, we will learn to distinguish syntactical errors and learn how to interpret them.

Consider the code below.

```
#include <iostream>
int main() {
  std::cout << "Hello world!"
  return 0;
}
```

When you save this source code into hello.cc and compile it, you will see this error:

```
hello.cc:4:29: error: expected ';' after expression
  std::cout << "Hello world"
                            ^
                            ;
1 error generated.
```

We know that this is a syntactical error because the first part of the error describes the file and what part of the file causes the error: hello.cc:4:29

The message means that the error is found inside the file we created called hello.cc. The numbers 4:29 refer to the line number (4) and column number (29) that is most likely causing the error. The message also gives visual a hint indicating that the error is after the close quotation mark.

The message also gives some suggestions for fixing the error. In this case, it says that it expected a ; after the statement. If you open Atom, you will see the line number and column where your cursor is currently located. You can move the cursor and look at the line and column numbers to help you locate the error and make some fixes to your code.

The errors you will see in the future may look different and in some cases, the hints may not always be as easy to understand. However, this process gives a good first step for locating and fixing errors.

<a id="runtime-errors"></a>

## 1.4. Runtime errors

Arguably, the most difficult type of error to fix is a runtime error. This is because the operating system and the compiler cannot detect these errors. The programmer needs to manually spot the error, identify the cause of the error, and make a fix.

Imagine you successfully compile and run your program. However, this is what you see on the screen.

```
Hello wold
```

Can you spot the problem?

If you notice, the error is the missing letter " r" . This seems like a trivial error, but this emphasizes the point that these are errors that happen when your program is already running.

We want to get rid of logical errors as much as possible because it is harder to take back your software once your user has run it. Imagine running Microsoft Word, and then seeing the splash screen saying Microsoft Wood instead.  Obviously, there are more critical logical errors like those that result in application crashes and security issues. For example, some runtime errors are so bad that they may even cause your program to crash!

```
Segmentation fault (core dumped)
```

Again, these errors are hard to detect because they don't produce error messages during compilation. Programmers need to manually run and test every aspect of their program to uncover the bug..

In a future module, we will learn about unit testing, which helps automate the process of manually checking your program. In the mean time, we will have to manually check our programs even after it successfully compiles and executes.

<a id="debugging"></a>

# 2. Debugging

After successfully completing this module, students will be able to:

- Distinguish between debugging compile errors, command-line errors, runtime errors, and logical errors.
- Correct command-line errors.
- Correct compile errors.

<a id="categorize-debugging-activities"></a>

## 2.1. Categorize Debugging Activities

In 1947, a team of computer scientists at Harvard University found that their program had a  logical error . It was producing confusing, incorrect outputs. They examined their computer, and found that a moth had become trapped in the wiring. The team's leader, programming language designer Grace Hopper , called the problem a "bug". She coined a phrase: problems with computer software are called bugs .

Debugging is the process of understanding and fixing bugs. Recall that Testing is the process of checking that a program works. We expect thorough Testing to identify many bugs. After our Testing identifies a bug, we perform Debugging to fix the underlying problem.

Testing can identify four categories of problem. There is a separate method of debugging for each category of problem.

1. Compile errors: Recall that you run the clang++ shell command in order to compile source code, to create an executable program. When clang++ provides no output, it succeeded, and there are no compile errors. However, if clang++ prints anything out, that means there is a syntax error in your code. To resolve this issue, we debug a compile error .
2. Command-line error: Recall that we use additional shell commands ( cd, ls, mkdir, mv, cp, rmdir, rm, and git) . These commands need to be typed in particular ways. They can only work when prepared properly. For instance, the cd command moves into a directory; it cannot work if that directory does not exist yet. When a command prints an error message, we debug a command-line error .
3. Runtime error: Recall that when we are Testing, after we have compiled a program, we run the program against test cases to see whether the program works. Often a program crashes, meaning that it encounters an error that is so severe that the program cannot continue running. When a program crashes, the environment provides a runtime error, which says what went wrong. When we run our program and it crashes, we debug a runtime error .
4. Logic error : A logic error occurs when a program does not crash, but still behaves incorrectly. The most common kind of logic error is incorrect output. In our testing, when a program finishes without crashing, but it prints output that does not match the test's expected output, that is a logic error. Another kind of logic error is returning the wrong exit code. When we run our program and it behaves incorrectly, we debug a logic error.

The first step in debugging is to distinguish between these four categories and choose the proper one. The action that you took that caused the error to appear determines which kind of debugging you need to do.

1. If clang++ caused the error, debug a compile error.
2. If a shell command (not clang++ and not your own program) caused the error, debug a command-line error.
3. If your program crashed, debug a runtime error.
4. If your program did not crash, but produced incorrect output, debug a logic error.

This module focuses on debugging compile errors and command-line errors.

<a id="debugging-command-line-errors"></a>

## 2.2. Debugging Command-Line Errors

Recall that a command-line error occurs when you use a shell command (other than the compiler or your own program) and it reports an error message. There are two reasons why this might occur:

1. Usage error: The command wasn't typed in properly. You could have typed too many arguments, too few, typed them in the wrong order, or simply made a typo (very common!).
2. Configuration error: The command cannot do what you asked because your environment is not ready for that. This happens when you skipped an earlier command, or did not notice that an earlier command failed.

The practice of debugging command-line errors is described in the following diagram.

Follow these steps:

1. Identify the error message: Read the output of the command in the shell.
2. Distinguish between a usage and configuration error: Is the message saying that you typed the command incorrectly, or that it cannot do what you asked? If you cannot tell, (If you have a partner) Discuss the message with your partner. Consult your journal. Have you encountered this message in the past? If so, how did you solve the problem? Consult the reference documentation for the command. If you are debugging a git error, read the Pro Git Book . For all other commands, search manpages.ubuntu.com . If you still cannot tell, ask an expert (instructor or lab assistant) for help. Be prepared to show them which command failed; the command's error message; your journal; and the websites you consulted.
3. Fix usage error: This means that you typed the command incorrectly. You need to try a different way of typing, which is hopefully correct. If an improvement occurs to you, go ahead and try re-entering the command. If not, seek information from the same sources as the previous step: Discuss with your partner (if you have one) Consult your journal Consult reference documentation Ask an expert
4. Fix configuration error: This means that the command understood what you typed, but following through is currently impossible. This happens when the files that the command affects are missing or are misconfigured because an earlier command failed or was skipped.

<a id="activity-debug-command-line-errors"></a>

## 2.3. Activity: Debug Command-Line Errors

This activity is an opportunity for you to practice debugging command-line errors.

The goal of this activity is for you to clone the C++ hello world source code at https://github.com/mucsi96/cpp-hello-world onto your computer, compile the program, and run the program. We tell you the commands to execute to do this. However, the commands will not work on the first try. Each command suffers from a usage or configuration error.

Your task is to follow the the process to debug these command-line errors, so that each command succeeds. You must work through these steps one at a time, in order. It is important that you get one step to work, without error messages, before moving on to the next. If you skip a step, that will cause configuration errors.

### Git Clone

Open a terminal window, then enter the following command:

```
~$ git https://github.com/mucsi96/cpp-hello-world.git
```

The gray box above indicates that this is a command that you should type. You type everything after the $ dollar-sign, then press the Enter key.

The command contains an error and produces an error message:

```
git: 'https://github.com/mucsi96/cpp-hello-world.git' is not a git command. See 'git --help'.
```

Debug the command-line error. When the command works, it produces output like the following (your version might enumerate a number of objects different from 37, this is not an error):

```
Cloning into 'cpp-hello-world'...
remote: Enumerating objects: 37, done.
remote: Total 37 (delta 0), reused 0 (delta 0), pack-reused 37
Unpacking objects: 100% (37/37), done.
```

### Move Into Directory

When git successfully clones the cpp-hello-world repository, it creates a directory called cpp-hello-world that contains the main.cpp source file we want to compile. The next step is to move into the cpp-hello-world directory with the cd command.

Enter the following command:

```
~$ cd cpphelloworld
```

The command produces an error message:

```
bash: cd: cpphelloworld: No such file or directory
```

Debug the command-line error. When the command works, it produces output like:

```
~/cpp-hello-world$
```

The cd command itself produces no output, and the terminal prompt shows that you are now inside the cpp-hello-world directory.

### Compile

GitHub repositories are intended to store source code, not binary executable programs. Adding binary programs to GitHub repositories is considered improper and wasteful. Therefore, the cpp-hello-world repository does not have a binary executable. In order to run the Hello World program, we need to compile the main.cpp source file ourselves with the clang++ command.

Enter the following command:

```
~/cpp-hello-world$ clang++ main
```

The command produces an error message:

```
clang: error: no such file or directory: 'main'
clang: error: no input files
```

Debug the command-line error. When the command works, it produces no output, so you will only see the command prompt again:

```
~/cpp-hello-world$
```

### Check That Program Exists

When clang++ succeeds at compiling a program, it creates a binary executable program that we can run. By default, this program file is named a.out. We did not override the default, so if the clang++ command above succeeded, our current directory contains a file named a.out.

Enter the following command:

```
~/cpp-hello-world$ ls
```

This one does not have an error, and should work properly.

The ls command lists all files in the current directory. If a.out does exist , the output of ls looks like:

```
a.out LICENSE main.cpp makefile README.md screen.png
```

If a.out does not exist, the output looks like:

```
LICENSE main.cpp makefile README.md screen.png
```

The only difference is that a.out is missing.

Identify whether or not a.out exists. If a.out does exist, proceed to the next step. If a.out does not exist, go back to the previous step and continue debugging until the clang++ command succeeds at creating a.out.

### Run Program

Finally, run the a.out program.

Enter the following command:

```
~/cpp-hello-world$ a.out
```

The command produces an error message:

```
a.out: command not found
```

Debug the command-line error. When the command works, it produces output like:

```
Hello World!
```

### Conclusion

At this step, you successfully

1. Cloned a repository full of source code onto your computer
2. Moved into the repository directory
3. Compiled source code into a binary executable program
4. Ran the program

Along the way, you debugged several command-line errors.

Congratulations! You will repeat many, if not all, of these steps every time you program. In particular, debugging command-line errors is a a kind of problem-solving that is essential to programming.

<a id="debugging-compile-errors"></a>

## 2.4. Debugging Compile Errors

When you use the clang++ command, the clang++ compiler:

1. examines your source code;
2. checks the source code for syntax errors ;
3. if there are syntax errors: print compiler messages in the terminal
4. otherwise (no syntax errors): create a program executable, named a.out by default

When there are no compiler messages, we say that the source code compiled cleanly . When we write programs, our goal is to write source code that compiles cleanly. It is difficult to do this on the first try. Usually, our first draft does not compile cleanly, and we need to debug compile errors several times before our code compiles cleanly.

Syntax is the system of rules for writing source code. For example, one syntax rule in C++ is that every statement must end in a ; semicolon. Another syntax rule is that every { open-brace must have a corresponding } close-brace. A syntax error is part of source code that disobeys a syntax rule. A syntax error makes it unclear what a program is supposed to do. A syntax error prevents the compiler from being able to create an executable program. When the compiler detects syntax error(s), it prints out the location and description of each syntax error, so that you can fix them. This list of the locations and descriptions of errors are called compiler messages.

There are two kinds of compiler messages:

1. An error message is so severe that the compiler cannot proceed with compiling the program. An error message is a "dealbreaker."
2. A warning message indicates a syntax error that is less severe. Even though there is a syntax error, the compiler is able to guess at what the program should do. Warning messages do not block the compiling process.

We must fix all error messages and warning messages before we certify that a program compiles cleanly. It might be tempting to overlook warning messages since they do not block the compiling process. However, when source code suffers from warning messages, that means that the compiler is guessing at what the program should do. It is very possible that these guesses are wrong, and the program has logic errors. Treat warning messages as helpful hints: the compiler is telling you about possible logic errors that need to be fixed.

Sometimes a syntax error confuses the compiler so much that starts seeing syntax errors that aren't actually there. We call this a domino effect. Only the first compiler message is trustworthy. Compiler messages after the first are suspect; they may or may not reflect actual syntax errors. For this reason, when we get multiple compiler messages, we focus on fixing only the first message . Trying to fix the later messages could be a waste of time. So we identify the first message, try to fix it, and compile again to see an accurate list of the remaining syntax errors.

Compiler messages look like this:

```
main.cpp:7:11: warning: missing terminating '"' character [-Winvalid-pp-token]  cout << "hello world;          ^main.cpp:7:11: error: expected expression1 warning and 1 error generated.
```

The output above contains one compile warning and one compile error. The last line of output is a summary of the number of warnings and errors.

Each message follows a pattern:

```
FILENAME : LINE : COLUMN : warning/error : MESSAGE
```

- FILENAME is the source code file that triggered the message. In this example, the source code is in a file named main.cpp, so all the messages originate from main.cpp
- LINE is the line number within FILENAME where the syntax error was found. Both messages originate from line 7.
- COLUMN is the column number within FILENAME where the syntax error was found. Both messages originate from line 11.
- warning/error indicates whether the message is a compile warning or compile error. We always fix both kinds, so we disregard this information.
- MESSAGE is a text description of the nature of the syntax error. The compiler does its best to explain the syntax error clearly, but sometimes the messages are not entirely clear.

Take a moment to check your understanding. Identify the FILENAME, LINE, COLUMN, warning/error, and MESSAGE part of each of the two messages above.

The process for debugging a compile error is described in the flowchart below:

In words, the process is:

1. Look at the compiler messages, and identify the... first message (ignore the others) source file line number column number message
2. In your text editor, navigate to the file, line, and column for the message.
3. Think about what is written in the source code, the syntax rules, and the message. Do you understand how to fix the syntax error?
4. If yes (do understand): use the text editor to change the source code to fix the problem; save; and try compiling again.
5. Otherwise (don't understand): use your information sources to better understand the syntax error. Discuss with your partner Check your journal Use reference documents to define terminology If you still don't understand the syntax error, ask an instructor or lab assistant for help

<a id="activity-debug-compile-errors"></a>

## 2.5. Activity: Debug Compile Errors

This activity is an opportunity for you to practice debugging compile errors.

Each of the following source code files has one or more syntax errors. Your task is to follow the process to debug compile errors for each file. You are finished when every single source file compiles cleanly.

1. part1.cpp
2. part2.cpp
3. part3.cpp
4. part4.cpp
5. part5.cpp

<a id="design"></a>

# 3. Design

After successfully completing this module, students will be able to:

- Understand a programming problem
- Design a solution to a programming problem
- Write a solution to a programming problem.
- Debug logical errors

<a id="steps-for-solving-a-programming-problem"></a>

## 3.1. Steps for solving a programming problem

We will follow the flowchart below to guide us to solve a programming problem.

<a id="dissecting-a-programming-problem"></a>

## 3.2. Dissecting a programming problem

There is no one tool to solve all problems. In the same way that we don't use a hammer to fix all problems, there is no one programming construct to solve all problems. Can you imagine fixing a broken windshield with a hammer?

The first step in solving a programming problem is to read and understand its requirements. If we can extract the key aspects of the problem we can identify the right programming constructs (tools) for the job. Here are some simple steps that can help you find the important aspects of the problem.

1. Understand the problem Read the problem at least three times and take notes. This will help us make sure we understand the problem and what we need to do. It is a good idea to write questions you might have as you read the problem. This will help us uncover its important aspects. When you find an answer to a question as you read or reread the problem, update your notes.
2. Identify the inputs. All programs will require some form of input. It can either be an initial provided value, a value provided by the user from the command line or graphical interface, or retrieved from a data source (e.g., file or database).
3. Identify the outputs. All programs will also have an end goal. You will need to find a way to manipulate the inputs to produce the expected output. If we don't know what output to expect, then we won't know how to manipulate the inputs and therefore what programming constructs to use.
4. Identify test cases (simple and edge cases). It is easier to solve problems when we have actual inputs and outputs. Compile a list of simple and edge cases for the problem. Edge cases refer to situations that involve rule exceptions or special handling of inputs to produce the expected output. We test for edge cases because a developer is more likely to implement them incorrectly. A simple case for a division program might take in 8 and 2 which involves simple division without any foreseeable errors. An edge case may take in a 3 and 0 which the developer needs to handle to avoid a division by zero error. It's good practice to create tests for categories of input/outputs. For example, you can have only one test for positive inputs, but you have a separate check for negative inputs. There are no specific requirements on how many test cases you need, but do your best to consider as many as possible. It's ok if you can't think of everything. You'll discover more cases as you move on to the later steps in the process. As you think of test cases, you may also notice that some details are missing from the problem. Sometimes you can infer this from the problem, but it is probably a good idea to ask your instructor or whoever gave the problem to verify. Asking these questions can lead to interesting discussions and help you find the appropriate solution.

<a id="dissecting-a-programming-problem-example"></a>

### Example: Dissecting a programming problem example

Let's apply what we just learned on the programming problem below. Perform each step and click on the buttons to compare your answers with some possible answers.

```
Create a program that computes the quotient of two numbers provided by the user. The program will first ask the user to input two numbers then display the result on the screen.
```

1. Understand the problem

See examples of notes

```
1. Where do I get the inputs? -> The user will provide them
2. What kind of data is provided? -> Numbers
3. What operations would I need to perform? -> Quotient refers to division
4. What do I do with the quotient? -> Display them on the screen

```

2. Identify the inputs

See examples of inputs

```
Two numbers
```

3. Identify the outputs

See examples of output

```
Display the quotient of the two given numbers on the screen. 
```

4. Create simple and edge cases

See simple and edge case examples

```
Simple cases:
1. 8 and 2 -> 4
2. 4 and 2 -> 2
3. 10 and 10 -> 1

Edge cases:
1. 1 and 4 -> 0.25
2. -4 and 2 -> -2
3. 5 and 0 -> Not sure. Perhaps we can return 0 or -1? Let's verify this with our instructor.

```

<a id="develop-a-plan-to-solve-the-problem"></a>

## 3.3. Develop a plan to solve the problem

A good strategy to solve the problem is to describe the solution instead of coding it straightaway.

1. Express the solution in an understandable form. Imagine how you would solve the problem and express it in a simple format. You can write a step-by-step process, create a decision tree, or draw an illustration.
2. Test your solution. Use your simple and edge cases to test your solution.
3. Revise solution. If you find errors in your solution after testing, rethink your solution with the issues in mind. Go back to #1.

A simply-formatted solution is easier to change than rewriting code. This is why we avoid starting with writing code.

<a id="develop-a-plan-to-solve-the-problem-example"></a>

### Example: Develop a plan to solve the problem example

Let's apply what we just learned on our programming problem. Perform each step and click on the buttons to compare your answers with some possible answers.

```
Create a program that computes the quotient of two numbers provided by the user. The program will first ask the user to input two numbers then display the result on the screen.
```

### Express the solution in an understandable form

See example of simple solution formats.

Let's create a step-by-step process for solving this problem. Your answer might look like:

1. Ask the user for the first and second number and store them.
2. Multiply the first number by the second number and keep the result.
3. Retrieve the stored value and display the result.

### Test your solution

See example of testing.

Let's now try out this process for a number of examples that we previously identified

Given 8 and 2:

1. Store 8 and Store 2.
2. 8 multiplied by 2 is 16. Store 16.
3. Display 16.

### Revise solution

See example of revision.

The output is incorrect because we got 16 instead of 4. Recall that our simple case of 8 and 2 should have given us 4. This probably means there's a mistake in the operation. We correct the operation by switching it to division. Here's our revised process.

1. Ask the user for the first and second number and store them.
2. Divide the first number by the second number and keep the result.
3. Retrieve the stored value and display the result.

Given 8 and 2:

1. Store 8 and Store 2.
2. 8 divided by 2 is 4. Store 4.
3. Display 4.

Given 1 and 4:

1. Store 1 and Store 4.
2. 1 divided by 4 is 0.25. Store 4.
3. Display 0.25

<a id="identifying-appropriate-constructs"></a>

## 3.4. Identifying appropriate constructs.

The challenging part in translating a plan to code is identifying the appropriate constructs to implement the plan. As you learn more about C++ you will observe that certain constructs are appropriate for implementing specific behaviors. The table below shows some of these mappings, but it will be good for you to grow this list over time. Think of the table as your toolbox of C++ constructs that you can refer to whenever you are implementing a plan.

|C++ Construct|Purpose|
|---|---|
|variables|Used to store information|
|cin|Used to retrieve user's input into a variable|
|cout|Used to display values on the screen (including variables)|
|arithmetic operators|Used to apply arithmetic operations such as addition, subtraction, multiplication, division, etc.|
|if statement|Used to decide whether to perform an action|
|if-else statement|Used to decide whether to perform one action if a condition is satisfied or perform another action otherwise.|
|nested if statement|Used to decide which action to perform according to a given condition.|
|for loop|Used to perform an action repeatedly for a given number of repetitions.|
|while loop|Used to perform an action repeatedly while a certain condition is true.|

<a id="identifying-appropriate-constructs-example"></a>

### Example: Identifying appropriate constructs example

We have a solution so now let's figure out which C++ constructs to use. Identify the C++ construct you think you will use for each step of the plan. Click on the buttons to compare your answers with some possible answers.

#### 1. Ask the user for the first and second numbers and store them

See possible C++ constructs.

1. variables (to store data)
2. cout (ask user for input)
3. cin (retrieve user input and store to a variable)

#### 2. Divide the first number by the second number and keep the result.

See possible C++ constructs.

1. arithmetic operators (division /)
2. variables (retrieve operands and store the result)

#### 3. Retrieve the stored value and display the result.

See possible C++ constructs.

1. cout (display the result stored in the variable)

<a id="write-code"></a>

## 3.5. Write code

Let's recall all information we have so far.

1. Ask the user for the first and second number and store them. --> variables (to store data), cout (ask user for input), cin (retrieve user input and store to a variable)
2. Divide the first number by the second number and keep the result. --> arithmetic operators (division /), variables (retrieve operands and store the result)
3. Retrieve the stored value and display the result. --> cout (display the result stored in the variable)

We should now have everything we need to write our code. We often start with the basic C++ template below. Our code will go inside the main block. Code in the main block is the first thing that the computer will perform.

```
#include <iostream>
int main() {
  return 0;
}
```

We then apply our selected constructs to perform the behavior we intended.

Step 1:

```
// variables
double num1 = 0;
double num2 = 0;
double quotient = 0;

// ask user for input and store them
std::cout << "Please input first number: ";
std::cin >> num1;
std::cout << "Please input second number: ";
std::cin >> num2;

```

Step 2:

```
// perform division and store them
quotient = num1 / num2; 

```

Step 3:

```
// Display results
std::cout << quotient;
```

Here is the final code

```
#include <iostream>
int main() {
  // variables
  double num1 = 0;
  double num2 = 0;
  double quotient = 0;

  // ask user for input and store them
  std::cout << "Please input first number: ";
  std::cin >> num1;
  std::cout << "Please input second number: ";
  std::cin >> num2;

  // perform division and store them
  quotient = num1 / num2;

  // Display results
  std::cout << quotient;  return 0;
}

```

<a id="testing-and-debugging-logical-errors"></a>

## 3.6. Testing and Debugging Logical errors

### Code tracing

Code tracing involves testing the cases we previously identified and imagining how the computer would run your code line by line. We use the inputs on the operations from our solution and compare our expected results with the values from our test cases. Although we could have directly compiled and run the program, tracing it manually helps us understand our code better. It will help us debug our code later.

### Compilation and execution

We should now be ready to compile and execute our code. We follow the compilation and execution process from Module 1.

Don't worry if your code doesn't run perfectly the first time. We've learned about the different types of errors during compilation and execution from Module 2. We've also learned to debug and fix command-line and compilation errors from Module 3.

### Debugging Logical errors

If you recall, we discussed runtime errors, which are errors that are not easily detected during compilation and execution. These errors come up while you run the program resulting in program crashes or unexpected behavior.

By now, we have a good understanding of our code so we should not have a difficult time debugging and fixing it. The best way to uncover errors in our implementation, or logic errors, is to identify the input that caused the error and identify the expected output or behavior of the program. Go back to Step 1 and see if the new information changes your understanding of the problem, changes the inputs, changes the outputs, or changes the cases. In case of minor changes, you may need to simply tweak your solution and continue with the next steps. For example, you just need to change the number of decimal places shown on the screen. However, if there are major changes then you may need to rethink your plan so that it considers the new information. For example, you might not have considered an edge case so you need to add a new conditional statement.

Although it sounds like a lot of work, it is good practice to revisit your solution with new information. Tweaking the code may solve one case, but it could introduce errors with other cases that used to work. You may end up going back and forth between working and breaking test cases so it is good to take a step back and revisit your plan instead. Otherwise, you may be trying to use a plan that will never solve the problem (e.g., using a condition instead of a loop).

Programming is iterative and you don't always solve problems in one go. If you recall our flowchart we see that we can jump from testing and back to dissecting the problem. We repeat the steps until we are able to successfully run our program without errors.

<a id="reference"></a>

# 4. Reference

After successfully completing this module, students will be able to:

- Identify whether they need to define a technical term; clarify a syntax rule; or discover a new tool (syntax/function/class).
- Find the definition of a technical term in reference documentation, and restate the definition in their own words.
- Find a syntax rule in reference documentation, and restate the rule in their own words.
- Search for a new tool (function or class) in reference documentation, and incorporate the tool into a design.
- Write a technical question for an expert including the What, Where, and How of the issue.

<a id="identifying-what-you-need-from-reference-material"></a>

## 4.1. Identifying What You Need from Reference Material

Sometimes while programming we get stuck because we lack information. This is a natural part of the process. Programming languages have hundreds of terms, syntax elements, functions, and classes. It is not practical for a person to memorize all of these details. Inevitably we need to use reference material to find information.

Using reference material is essential for self-sufficiency and longevity as a programmer. Your instructor is happy to help, but it is simply impossible for them to address every doubt in a large class. We hope that you will continue programming after the class ends, in a more advanced class, job, or personal project; your instructor will be unavailable at that point. And, technology changes over time. The C++ language adds new elements as it evolves. Software developers create new languages and APIs to write code for newly-invented technologies. In order for your programming skills to remain relevant, you need to be able to find information in reference material.

The process for using reference material is described in the flowchart below.

Other flowcharts tell you to use reference material in four specific situations:

1. When you are Debugging a compiler message and do not understand one of the words in the message.
2. When you are Debugging a command-line usage error and do not remember the usage rules for the command.
3. When you are Debugging a compiler message and do not remember a syntax pattern.
4. When you are Choosing a Tool to write code, and cannot think of any syntax element, function, or class to use.

This corresponds to the four ways that we use reference material:

1. define technical term
2. clarify command usage
3. clarify syntax
4. discover tool

For us, the phrase "reference material" includes:

1. documentation , which are authoritative text documents; and
2. asking questions of experts, namely your instructor.

As you can see in the flowchart, you start out consulting documentation. Usually you can find your answer that way on your own. If consulting documentation does not answer your question, your next step is to ask a question of an expert. We prioritize documentation to be respectful of experts' time, and to work efficiently. Consulting documentation takes only one person's attention (yours), but asking a question takes two peoples' attention.

The first step in using documentation is to identify which of the four kinds of information you need (define technical term, clarify command usage, clarify syntax, or discover tool). Learn about how to find each kind in the following pages.

<a id="define-a-technical-term"></a>

## 4.2. Define a Technical Term

A technical term is a word that has a specific meaning in the context of a discipline. For example, "program" is a technical term in the context of computer science. When doing computer science, "program" means an executable file that a computer can run. "Program" has different meanings in other contexts. For example, a schedule for a play is called a program, and a government initiative such as Social Security is a program. Using technical terms accurately facilitates communication. Compiler messages, documentation, and questions rely on technical terms to convey complicated ideas concisely. This is why we emphasize vocabulary.

You define a technical term when you encounter a technical term that you do not understand. The Debugging flowchart tells you to define a technical term when you don't understand a word in a compiler message. You might also need to define a technical term to comprehend documentation or expert question answers.

A glossary is a document that contains definitions of technical terms. We recommend using Bjarne Stroustrup's C++ Glossary. (As you may know, Bjarne Stroustrup is the inventor of C++.)

A glossary is organized in alphabetical order. Symbols like # come before letters. You can use the find feature in your browser (CTRL-F or ⌘ -F) to quickly jump to the term you are seeking. For example, the definition of "operator" is:

operator - conventional notation for built-in operation, such as +, *, and &. A programmer can define meanings for operators for user-defined types. See also: operator overloading, unary operator, binary operator, ternary operator, prefix operator, postfix operator. TC++PL 6.2.

This definition contains links to the definitions of other technical terms, including user-defined types and operator overloading. You can follow these links to learn about the related terms.

Before moving on, find and read the glossary definitions for the following technical terms:

1. expression
2. lvalue
3. rvalue
4. statement

Take a look at the Use Reference Material flowchart, and focus on the part about defining a technical term, on the left.

As you can see, if you are still confused about a technical term after consulting the glossary, your next step is to Ask A Question. We will get to that soon.

In summary, the process to define a technical term is :

1. Visit the Bjarne Stroustrup's C++ Glossary webpage.
2. Find the term you are defining, and read its definition.
3. If technical terms in the definition confuse you, find and read their definitions.
4. If you are still confused, Ask A Question.

<a id="clarify-command-usage"></a>

## 4.3. Clarify Command Usage

Recall that we type commands into the terminal. Common commands include cd, ls, and clang++. A s discussed earlier in Step 3: Command line errors , a usage error happens when we enter a command improperly. This might be because we typed in too many arguments, not enough arguments, or typed them in the wrong order.

According to the Debugging flowchart, you should first try to clear up a usage error by discussing it with your partner, then consulting your journal. If you are still confused after those steps, then you should follow the instructions in this page to clarify command usage .

### Finding Manpages

Each command is explained in a piece of documentation called a manpage . This is an unusual technical term that is short for man ual page . Together, all of the manpages form a kind of "manual" for the shell environment.

You can read manpages at the website https://manpages.ubuntu.com . Enter the name of the command you are clarifying into the search box on the top-right corner of that page.

The next page asks you which version of the manpage you want to view. It does not matter because command usage rarely changes, if ever. You might as well pick the most recent version, which is the rightmost link.

The next page is the actual manpage that describes a command.

### Interpreting SYNOPSIS

A manpage has a SYNOPSIS section that explains the usage rules for writing arguments. The synopsis uses a particular notation to describe the order of arguments, which arguments are required, and which are optional.

Let's examine the synopsis for the mkdir command, which creates a directory.

```
SYNOPSIS       mkdir [-p] [-m mode] dir...
```

Observe that

- the arguments mode and dir are underlined,
- square brackets [ ] enclose some arguments, and
- there is an ellipsis (three dots ...).

Underlining, square brackets, and ellipses have specific meanings:

|Notation|Example|Meaning|
|---|---|---|
|Underlined argument|dir|The argument is a fill-in-the-blank|
|Square brackets|[-mmode]|The arguments between parenthesis areoptional(all or nothing)|
|Ellipsis|dir...|The argument may be repeated|

A fill-in-the-blank means that you write something in place of the underlined argument. The usage rules for fill-in-the-blanks are explained in the DESCRIPTION and OPTIONS sections below. In our example, dir is the name of the directory to create, so in

```
$ mkdir part1
```

the argument part1 is filling in the dir blank.

All or nothing means that you may choose to write all of the arguments between brackets, or none; you cannot write only some of them. So [-m mode ] means that you may omit both -m and mode ; or you can write both -m and mode ; but you may not write -m by itself, or mode by itself. For example,

```
$ mkdir part1
```

follows the rules because -m and mode are both omitted. Also,

```
$ mkdir -m 755 part1
```

follows the rules because both -m and mode are include (755 fills in the mode blank). But

```
$ mkdir -m
```

is not valid because -m is given but mode is not.

A repeated blank can be filled in more than once. For example,

```
$ mkdir part2 part3 part4
```

creates fills in the dir three times to create three directories part2, part3, and part4 all in one command.

### Interpreting DESCRIPTION

The DESCRIPTION section comes after the SYNOPSIS. The DESCRIPTION section explains what the command does, and the meaning of the required fill-in-the-blanks.

For example, the DESCRIPTION of mkdir is:

```
DESCRIPTIONThe  mkdir  utility  shall  create the directories specified by the operands, in the order
       specified.

       For each dir operand, the mkdir utility shall perform actions equivalent  to  the  mkdir()
       function  defined  in  the  System  Interfaces  volume  of  POSIX.1‐2017,  called with the
       following arguments:

        1. The dir operand is used as the path argument.

        2. The value of the bitwise-inclusive OR of S_IRWXU, S_IRWXG, and S_IRWXO is used as  the
           mode  argument. (If the -m option is specified, the value of the mkdir() mode argument
           is unspecified, but the directory shall at no time have permissions  less  restrictive
           than the -m mode option-argument.)
```

The gist of this is that mkdir creates each of the dir arguments that were entered.

### Interpreting OPTIONS

The next section is OPTIONS, which details the meaning of the arguments listed in the SYNOPSIS.

For example, the OPTIONS section for mkdir is:

```
OPTIONSThe  mkdir  utility  shall conform to the Base Definitions volume of POSIX.1‐2017, Section
       12.2, Utility Syntax Guidelines.

       The following options shall be supported:

       -m mode   Set the file permission bits of the newly-created  directory  to  the  specified
                 mode  value.  The  mode  option-argument  shall  be the same as the mode operand
                 defined for the chmod utility. In the symbolic_mode strings, the  op  characters
                 '+'  and  '-' shall be interpreted relative to an assumed initial mode of a=rwx;
                 '+' shall add permissions to the default mode, '-' shall delete permissions from
                 the default mode.

       -p        Create any missing intermediate pathname components.

                 For each dir operand that does not name an existing directory, before performing
                 the actions described in the DESCRIPTION above, the mkdir utility  shall  create
                 any  pathname  components of the path prefix of dir that do not name an existing
                 directory by performing actions equivalent to first calling the mkdir() function
                 with the following arguments:

                  1. A  pathname  naming  the  missing pathname component, ending with a trailing
                     <slash> character, as the path argument

                  2. The value zero as the mode argument

                 and then calling the chmod() function with the following arguments:

                  1. The same path argument as in the mkdir() call

                  2. The value  (S_IWUSR|S_IXUSR|~filemask)&0777  as  the  mode  argument,  where
                     filemask  is  the  file  mode  creation  mask of the process (see the System
                     Interfaces volume of POSIX.1‐2017, umask())

                 Each dir operand that names an  existing  directory  shall  be  ignored  without
                 error.
```

This explains that the -m argument sets the "file permissions" of the new directories, and that you can find more information about that in the manpage for the chmod command. The -p argument causes mkdir to "create any missing intermediate pathname components." So in

```
mkdir -p path/to/subdir
```

-p means that mkdir will create path and to on the way to subdir, unless they already exist.

### Summary

In summary, the process to clarify command usage is:

1. Visit manpages.ubuntu.com and search for the command by name.
2. Read and interpret the SYNOPSIS section.
3. If you are still confused, read and interpret the DESCRIPTION section.
4. If you are confused about optional arguments, read and interpret the OPTIONS section.
5. If you are still confused, Ask A Question.

<a id="clarify-syntax"></a>

## 4.4. Clarify Syntax

As you know, syntax is the rules for writing program elements like if statements and for loops. Making syntax errors is a routine part of programming. When we compile source code with syntax errors, the compiler produces messages that describe the location and nature of the errors. Sometimes we can correct syntax errors based only on the compiler messages. But sometimes we need to remind ourself of syntax rules. When we clarify syntax , we find syntax rules in documentation to refresh our memory.

Take a look at the Use Reference Material flowchart, and focus on the part about clarify syntax (the third column from the left).

As you can see, the reference materials that we consult are, in order,

1. cppreference,
2. our textbook, and
3. Ask a Question.

### Finding a Page on cppreference.com

cppreference.com is a website containing documentation for the C++ language. It is not a textbook, so it is not meant to explain new ideas to beginners. Instead, it is a reference document for experienced programmers to find information quickly. We will use cppreference.com to clarify syntax and discover tools. This happens often, so it is a good practice to keep cppreference.com open in a browser while programming.

You can navigate to a relevant page by browsing or searching .

To browse , click on the link that is most relevant to the kind of syntax you are clarifying. Syntax topics are under the Language heading on the top-left.

For example, if you need to clarify how to write an if statement, you would click on the Statements link. That page clarifies the syntax for all forms of statements, including if statements.

To search , enter a search term in the text box in the top-right corner, then click Search.

### Finding the Relevant Section

You may need to scroll through the page, or use the find function (CTRL-F or ⌘-F), to find the section of the page that is relevant. If none of the page is relevant, you need to try a different page.

For example, the section that clarifies if statements is below.

### Finding the Relevant Pattern

There are five different patterns for selection statements, shown above. They are numbered (1) through (5). The number to the right of each pattern corresponds to the description in the numbered list below all the patterns. Looking at the list at the bottom, we see:

1) if statement;

This tells us that the pattern for an if statement is (1), not one of the other patterns. As another example, (3) is the pattern for switch statements.

### Interpreting the Pattern

Focusing on the relevant pattern (1), we see:

Like manpages, these pages describe syntax rules using a specific notation.

|Notation|Example|Meaning|
|---|---|---|
|bold text|if|write the text exactly as shown|
|italic text|statement|fill-in-the-blank|
|green (optional)|init-statement(optional)|this part is optional|

We follow this notation to decode a syntax rule.

Decoding the rule for if statements above, we see that an if statement needs to be written as the following parts in order:

1. optionally, an attr fill-in-the-blank; then
2. "if"; then
3. optionally, the "constexpr" keyword; then
4. an open-parenthesis "("; then
5. optionally, an init-statement fill-in-the-blank; then
6. a condition fill-in-the-blank; then
7. a close-parenthesis ")"; then finally
8. a statement fill-in-the-blank.

We won't use these optional parts in this course, so you can skip them. Leaving out the optional parts, the syntax rule for an if statement is

1. "if"; then
2. an open-parenthesis "("; then
3. a condition fill-in-the-blank; then
4. a close-parenthesis ")"; then finally
5. a statement fill-in-the-blank.

Reviewing this list can remind you how to write an if statement. Or, if you are confused by a syntax error, reviewing the list can help you identify the error. For example, a common syntax error is to forget the parenthesis in an if statement.

### Review Your Textbook

cppreference.com is intended to provide a quick refresher on syntax patterns, not explain them in detail. If you have interpreted the pattern and are still confused about the syntax rule, it is time to review your textbook. Re-read the relevant part of your textbook (for example, if you are still confused about if statements, re-read the section of your textbook that covers if statements).

If you are still confused after reading cplusplus.com and your textbook, it is time to Ask a Question.

### Summary

In summary, the process to clarify syntax is:

1. Use a web browser to visit cppreference.com .
2. Navigate or search to a page that is relevant to the syntax.
3. Find the section of the page that is relevant to the syntax.
4. Find the rule that is relevant to the syntax.
5. Interpret the rule; identify the mandatory parts, optional parts, and fill-in-the-blanks.
6. If you are still confused, re-read the relevant part of your textbook.
7. If you are still confused, Ask A Question.

<a id="discover-tool"></a>

## 4.5. Discover Tool

When you choose a tool , you select the most applicable tool from the "toolbox" of tools you know.  For example:

- When you need to enter a shell command, you choose from our list of shell commands: pwd, ls, cd, mkdir, touch, rm, cp, mv, cat, and history.
- When you need to write a code statement, you chose from the kinds of statements: variable declaration, expression statement, selection statement, loop statement, jump statement, or try statement.

We planned this course so that you will learn about tools before you need them. So when you are doing assignments, that planning is perfect, and your recollection of tools is perfect, you will always be able to choose an applicable tool. However, if that is not the case, you will need to discover a tool . In particular, you will need to discover a tool if you forget about some of the tools on the list, or you are working on projects outside of class. Discovering tools is a big part of the job of being a software developer!

### Which Kind of Tool?

This module covers discovering C++ syntax rules, functions, and classes to use while writing code. You can also discover other kinds of tools, such as shell commands, but that is not covered here.

To be clear, the kinds of tools that you might need to discover are

- syntax rules for code elements such as selection statements, loops, exceptions, etc.;
- functions to call, such as stoi and rand; and
- classes to use, such as string and vector.

Ignore any kind of tool you haven't learned about yet. Anyone reading this should have learned about syntax, but you may not have learned about functions or classes quite yet.

Discovering a tool involves some problem solving and critical thinking. You need to search through documentation to find an applicable tool. The documentation may use different words that what you have in mind. For example, if you need a tool to create a calendar, you might be thinking of the word "calendar," but the documentation actually uses the phrase "date and time" for that sort of thing. So you need to read the documents carefully and exercise your reading comprehension skills to find an appropriate tool.

### Explore cppreference.com Table of Contents

The first place to explore is cppreference.com . Start with the table of contents on the front page.

Read the list of topics. As you go, think: "might this be relevant to what I'm trying to do?" Click on any page that sounds promising.

You may find this to be slow the first time you do this. However, as you explore these pages and become familiar with their contents, searching through the table of contents will get faster and faster. This is one way that C++ programmers become knowledgeable about the tools in the language. Navigating documentation is a muscle that gets stronger when it is exercised.

### Explore Algorithms Library

If the table of contents did not lead you to an applicable tool, double check the algorithms library .

The algorithms library contains a long list of functions. Each function is a useful general-purpose tool. There is a good chance that one of these functions is the tool that you need.

Before moving on, find a function in the algorithms library that does each of the following things.

1. exchange the contents of two variables
2. calculate the maximum of two numbers
3. copy the elements of any array into a different array

### Search cppreference.com

If you still haven't discovered an applicable tool, use the Search feature on cplusplus.com.

If your first search does not turn up any applicable pages, you may need to try searching again with different words for the same thing. Remember, the terms used in the documentation pages may be different from what comes to your mind.

### Explore Textbook

If you still haven't discovered an applicable tool, search your textbook for a relevant tool.

As you did for cplusplus.com, look over the textbook table of contents, and ask yourself: "might this be relevant to what I'm trying to do?" Flip to the promising pages to decide whether they are applicable to your problem.

If the table of contents did not help, try the index. The index lists technical terms, and where they can be found in the textbook. Check the index for relevant terms and flip to promising pages.

### Ask A Question

If you still haven't discovered an applicable tool, it is time to Ask A Question. The next page explains how to Ask A Question.

### Summary

In summary, the process to discover a tool is below. Follow each step in order until you find a useful tool.

1. Explore the cppreference.com table of contents.
2. Search cppreference.com .
3. Explore the textbook table of contents.
4. Search the textbook index.
5. Ask A Question

<a id="ask-a-question"></a>

## 4.6. Ask a Question

When you Use Reference Material, your last resort is to Ask A Question . When you are unable to find the information that you need in reference documents (glossary, manpages, cplusplus.com) or the textbook, it is time to ask an expert for help.

Also, the debugging flowchart says to Ask A Question when you are confused by a compiler message or command-line error, and consulting reference documents did not help.

The computer science community includes many experts who want to help you solve your problems. However, you need to ask your question in a way that makes it possible for them to help. They need to know what specific problem you are having. You need to use precise technical terms so that your question is clear.

The same guidelines apply whether you are asking your question verbally face-to-face, in a synchronous message like Slack, or an asynchronous message like email.

### Productive Questions

Your goal is to ask a question that is productive , meaning that an expert can answer the question and solve your problem quickly. Questions that are not productive can cause miscommunications, waste time, and frustrate you and the expert.

A productive question...

1. comes after a good-faith effort to solve your problem yourself using the flowcharts;
2. is directed to the right person or place;
3. says what specifically you are trying to do;
4. says where you are on the flowcharts;
5. says how the problem arises; and
6. demonstrates proper etiquette .

### After a Good-Faith Effort

Asking a question is a last resort. You should follow the flowcharts to consult other resources before you Ask A Question.

As explained in Step 2: Identifying What You Need from Reference Material , w e prioritize documentation to make efficient use of everyones' time.

Also, as you will see below, the other steps help prepare you to ask a productive question.

Good instructors teach students how to be self-sufficient. Students learn to be self-sufficient by practicing solving their own problems. So your instructor will expect you to make a good-faith effort at solving a problem before they solve it for you.

Outside of class, you will be asking experts who are volunteers or coworkers. These people are not obligated to help you, and will be more inclined to answer your question if they feel that you have made a good-faith effort.

### Right Person

Just because someone is a helpful expert, that doesn't mean that they can answer every question that you might have. An expert in C++ programming can answer questions about C++, but may not necessarily be able to answer questions about other topics, such as artificial intelligence.

Here are some guidelines for asking the right person:

- When you are in a lab class, ask the class instructor or lab assistant.
- When your question relates to a class assignment, ask the instructor of that class.
- When your question relates to installing or troubleshooting Tuffix, ask in the Tuffix slack channel.

### What

Your question needs to communicate what specific task you are working on.

In the context of classwork, say

- which class (unless you are currently in class, and this is obvious);
- which assignment ; and
- which part of that assignment.

For example, an email might include the sentence "I am having an issue with CPSC 120 lab 8, specifically the part where I need to create an array."

Outside of classwork, say what kind of project or task you are asking about. For example, you might say "I am trying to write a C++ program that displays the current weather" or "I am trying to install Ubuntu Linux on a Raspberry Pi."

### Where

Say where you are on the flowcharts . The purpose of this is to communicate

- which of the practices you are stuck on (design, choose a tool, testing, debugging, or use reference material);
- the steps you have already tried , that have not worked; and
- when debugging , which kind of error you are facing ( compile error , command-line error , runtime error , or logic error ).

The main reason to communicate these things is to give the expert the information that they need in order to help. They will need to know all of this information anyway, so you might as well say it up front. You and the expert both want to resolve your question quickly, and being forthcoming about the problem minimizes back-and-forth communication. This is especially important in asynchronous messages (email) where each reply may take days.

A secondary reason is to convince the expert that you truly have already made a good-faith effort. As explained above, experts may not answer your question if it seems like you haven't made a good-faith effort yet.

### How

The "how" is the context of a debugging question. If your question is not about debugging, you can skip the How section.

If you are debugging, that is because something did not work. Compiling your code gave a compiler message, a shell command gave an error message, your program crashed, or your program failed a test case. Of course, you know what happened and what the error message was, because you were there when the error occurred a moment ago. However the expert was not there, so they cannot know this crucial information unless you tell them.

Say what triggered the error, and what the error message was:

- compile error: share the the first compiler message;
- command-line error: share the command you typed, and the error message;
- runtime error: share the test case you input to your program, and the error message;
- logic error: share the test case that you input to your program, the expected output, and the actual output of your program.

"Share" this information in a way that fits the medium of your question. If you are in an in-person class, you can point it out on your screen. Or, if you are writing a text message, copy-paste the information.

### Etiquette

You are asking a question in a college class or workplace, so your message should be appropriate for those settings.

Since you already made a good-faith effort that did not work, it is natural to feel frustrated. These are valid feelings. But the expert did not cause your problem, so it is unfair to direct hostility toward them. If you must express frustration, express it toward the problem at hand, not people. If your question comes across as argumentative or demanding, it will be very difficult for the expert to set that aside and enthusiastically answer your question.

Use etiquette appropriate for the medium of your question. When asking a verbal question, speak clearly in a respectful tone of voice. Give the expert a chance to respond without interrupting. When writing an email, start with a salutation (e.g. "Dear Professor,"), write complete sentences, and end with a signature (e.g. "Thanks, Ada"). Give the expert a chance to respond (at least two business days) before writing another followup email.

### Examples of Productive Questions

As you read these positive examples, confirm for yourself that each question...

1. comes after a good-faith effort to solve your problem yourself using the flowcharts;
2. is directed to the right person or place;
3. says what specifically you are trying to do;
4. says where you are on the flowcharts;
5. says how the problem arises; and
6. demonstrates proper etiquette .

#### In-Class Verbal Questions

"Hi, I finished today's lab and am trying to push my code to GitHub, but I'm having a command-line error. The command I ran is here (points at command in terminal), and the error message I'm getting is here (points at error message)."

"Hi, I'm working on the second program in today's lab. My code has a logic error because in the first test case of 1000 seconds, the output should be 0:16:40, but my program outputs 0:16:00."

#### Email Question

```
Greetings,I'm in your 120 class and am having trouble with project 1. When I compile with "make", I get the following compile error:main.cpp:8:11: warning: equality comparison result unused [-Wunused-comparison]    if (x == 0, y == 1) {        ~~^~~~I understand what it means about "equality" and "comparison" but I don't understand what it means by "unused".Thanks,Ada
```

### Examples That Need Improvement

As you read each of these negative examples, observe how they fail to meet guidelines 1-6 above.

#### In-Class Verbal Questions

"I'm stuck."

"Should I write an if statement next? Or is it a return statement?"

"I'm working on lab 6, but every time I try it, it doesn't work."

#### Email Question

```
Project 1 is ridiculous. It doesn't even work. You better fix this or there will be TROUBLE!
```

```
Hi,Do I need to use make or clang++?Thanks,Chuck
```

### Summary

In summary, Ask A Question when you are following the flowcharts to solve a problem, your attempts to solve it on your own have not worked, and the flowchart instructs you to ask an expert.

Ask a question that...

1. comes after a good-faith effort to solve your problem yourself using the flowcharts;
2. is directed to the right person or place;
3. says what specifically you are trying to do;
4. says where you are on the flowcharts;
5. says how the problem arises; and
6. demonstrates proper etiquette .

<a id="testing"></a>

# 5. Testing

After successfully completing this module, students will be able to:

- Explain the importance of testing programs before release.
- Identify provided test cases, and each case's input and expected output.
- Determine whether a program passes a specific test case.
- Determine whether a program is certified to pass all test cases.
- Describe bisection debugging.

<a id="the-need-for-testing"></a>

## 5.1. The Need for Testing

### Bugs

A bug is a problem with a program. If you have been using apps for a while, you have probably experienced a bug. The app might freeze, need to be restarted, lose your data, or refuse to do anything at all.

We create programs in order to help people. Bugs prevent that. If your program has too many bugs, users will be unable to use it productively, and may reject your program out of frustration.

### Commercial Ramifications

Commercial software is the term for programs that are sold as products. Paying customers expect a product to work properly. When commercial software has bugs, customers become dissatisfied. They may post negative reviews, ask for a refund, boycot the company, or involve consumer protection authorities.

A company can suffer long-term harm when it releases software with bugs. Windows Me had a lot of bugs, which contributed to Microsoft Windows losing dominance in favor of macOS, Linux, and other platforms. More recently, the game Cyberpunk 2077 was panned as a "buggy mess."

When you work for a commercial software producer, your employment and salary depend on the health of your employer. If you release programs with bugs, you put the livelihood of yourself and your coworkers in jeopardy.

### Human Life

Safety-critical systems are mechanisms that people depend upon for their health and safety. When these systems malfunction, people can be hurt or even killed.

Programs control many safety-critical systems including

- medical devices (pacemakers, prosthetics, hearing aids)
- medical diagnostic equipment (CAT scan, radiology)
- automobile safety features (backup camera, blind spot monitoring, anti-lock brakes)
- airplanes and air traffic control
- elevators
- security systems

People may use ordinary software in a way that makes it safety-critical. For instance, a calendar app may not immediately seem safety-critical. But if a person uses the calendar app to remind them to take medically-necessary medications, then the app is in fact safety-critical. If the calendar app does not give a reminder properly, it could cause a serious health problem.

Bugs in this software can cause real harm to people. In the 1980s, the Therac-25 disaster was an event in which a computer-controlled radiation therapy had a bug that caused it to emit too much radiation into patients' bodies, causing some of them to die. In 1996, the Ariane 5 rocket exploded due to an integer overflow bug. Software bugs have caused or contributed to numerous airplane crashes.

### Professional Responsibility

Professional software designers are responsible for making sure that a program is reasonably free of bugs before they release it.

We live in an imperfect world, and people are imperfect creatures, so we cannot expect programs to be truly perfect. Theoretical computer science has proven that some kinds of bugs are impossible to detect accurately , which is another reason that we cannot demand for programs to never have bugs.

However, avoiding bugs is crucially important, so we need to make a serious effort to find and correct bugs before releasing programs.

<a id="black-box-testing"></a>

## 5.2. Black-Box Testing

Black-box testing is a method for testing whether a program has bugs or not. It gets its name because the testing process does not look into the inner workings of the program. The person doing the testing does not look at the program source code, so as far as they are concerned, the source code cannot be seen. You could think of the source code being placed in a figurative opaque box during testing.

### Test Cases and Test Suites

A test case is a specific input to a program, and expected output.

To check a program against a test case, a programmer runs the program, gives the program the expected input, and observes whether the program produces the expected output. If the program does, it passes that test case. But if the program's output does not match, that is a logic error , and the program fails the test case.

A test suite is a list of test cases. A program is considered to pass the entire suite when the program passes every test case in the suite.

In order to test a program, developers invent a test suite. The goal is to ensure that the program has no bugs, so a test suite needs to be thorough . We need to feel confident that, if a program passes the suite, then it has no bugs. A thorough test suite has many cases, and includes extreme inputs (largest/smallest possible) and inputs that may be difficult for the program to handle correctly.

### Example: Temperature Conversion

Suppose that we are testing a program that converts temperatures from Fahrenheit to celsius. The following is a test suite for this program.

|Test Case|Input|Expected Output|
|---|---|---|
|1|32|0|
|2|212|100|
|3|98.6|37|
|4|0|-17.8|
|5|-1|-18.3|
|6|-100|-73.3|
|7|1000|537.8|

Test Case 1 says that, when you run the program and input 32 degrees Fahrenheit, the program needs to output 0 degrees celsius. If the program outputs a different number, such as 1 or 100, that is a logic error that needs to be debugged, and the program fails the test. In order to pass the test, the program needs to produce the expected output for all six test cases.

The suite is thorough because it includes

- noteworthy inputs 32 (freezing) and 212 (boiling)
- the safety-related input 98.6 (human body temperature)
- mathematically-tricky inputs 0 and -1
- extremely small input (-100 degrees)
- extremely large input (1000 degrees)

Since the suite is thorough, we can feel confident that a program that passes the suite works properly and does not have bugs.

### Confirmation Bias

The black-box testing approach helps us to avoid releasing buggy software due to confirmation bias . Confirmation bias is the tendency for people to seek and favor information that confirms their existing beliefs.

After spending a lot of time writing a program, it is natural to feel pride in your work, and believe that it is a good program that works properly. Confirmation bias means that you are prone to looking for evidence that your program works, but avoid evidence that the program has bugs . For example, you might run your program once, choose an input that your instincts tell you will work, and then conclude that your program has no bugs. However, that is inadequate! One or two examples are not enough to establish that a program always works.

The purpose of the test suite is to prevent sloppy testing and confirmation bias. Developers need to give concerted thought to creating a suite with many, varied, thorough test cases.

Often, the person who creates the suite is different from the programmer in order to prevent a conflict of interest. In many companies, programmers and test engineers are different people with different job titles.

<a id="test-flowchart"></a>

## 5.3. Test Flowchart

The process for testing is described in the flowchart below.

In words, the process is:

1. Compile source code with clang++. If there are compile errors, use the debug compile error flowchart to debug the compile errors before continuing.
2. First test case : Look at the test suite, and identify the first test case, its input, and expected output. Run your program with ./a.out . Provide the program with the test case input. If the program crashes, use the debug runtime error flowchart to debug the error. Observe the program output and decide whether the actual output matches the expected output. If the output does not match , declare that the program fails the test. Use the debug logic error flowchart to debug the error. Otherwise (the output does match ), repeat step 2 with the next test case.
3. If the program works correctly (meaning no runtime or logic errors) for every test case, declare that the program passes the test. You can certify that the program is ready to release.

<a id="debug-logic-error-flowchart"></a>

## 5.4. Debug Logic Error Flowchart

A logic error happens when a program produces incorrect output. When you test your program, you may observe a failed test case that counts as a logic error. You may also observe a logic error while writing a program, before you get to testing.

The suspicious input is the specific program input that caused the logic error to appear. The suspicious input is an important clue that helps you to debug a logic error. Before you can proceed with debugging a logic error, you need to identify the suspicious input.

### Flowchart

The flowchart for debugging a logic error is below.

In words, the process is:

1. Identify the suspicious input .
2. Trace the source code using the suspicious input. If you now understand why the code produces incorrect output, edit the source code and test again.
3. Otherwise, use bisection debugging to find where the program goes wrong. If you now understand why the code produces incorrect output, edit the source code and test again.
4. If you still do not understand why the program produces incorrect output, Ask a Question according to the Use Reference Material flowchart.

Recall that tracing means examining the source code and imagining how the program would run with the suspicious input.

Bisection debugging is explained on the next page.

<a id="bisection-debugging"></a>

## 5.5. Bisection Debugging

### The Idea

Bisection debugging is an approach for pinpointing where a logic error comes from. It is inspired by the binary search algorithm .

The idea is that a program with a logic error

1. works correctly for a while, then
2. at a certain point, does something wrong

The moment when the program does something wrong is called the fault . Once the fault happens, the program is doomed to produce incorrect output. Bisection debugging involves searching for the fault.

The suspicious area is the part of your source code that might contain the fault. To begin with, you have to assume that the suspicious area is everything . Then, we perform an experiment that shrinks the suspicious area. We repeat experiments until we narrow down the suspicious code to a single line. Then, we can fix the problem.

### An Experiment

The process for one experiment is:

1. Note the suspicious area (the lines of source code that could contain the fault).
2. Identify a line number near the middle of the suspicious area.
3. Add a cout statement at the middle. The statement should print A distinctive string like "DEBUG" The value of every variable in scope
4. Run the program with the suspicious input.
5. In the program output, identify your distinctive string (e.g. "DEBUG") and the value of all the variables.
6. Think about these values, and decide: do all of the variables have correct values?

### Narrow the Suspicious Area

An experiment tells you whether the the fault comes before or after the cout statement.

- If all of the variables have correct values, the fault is after the cout statement. Narrow down the suspicious area to be only after the cout.
- Otherwise (a variable is incorrect), the fault is before the cout statement. Narrow down the suspicious code to be only before the cout.

If you are still unsure about where the fault is, perform another experiment. Continue until you find the fault.

Every time you perform an experiment, the suspicious area shrinks by about half. That means that eventually the suspicious area is certain to be only a single line of code, and you know where the fault is. Since you are dividing the suspicious area in half each time, it takes remarkably few experiments to pinpoint the fault.

### Fix the Bug

At this point you have found the fault -- the line of code where the program starts misbehaving. The output of your cout statement shows the values of all variables at that moment. Use this information to determine what about the code is wrong, and how to change it so that it operates properly.

### Cleanup

You added some cout statements to your code to help with debugging. These are temporary additions that do not belong in the final program. When you are done with bisection debugging, delete all of the cout statements that you added for experiments.
