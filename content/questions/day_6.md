+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 6"
+++
## Preparation for day 6: 

Week two we will do demos and discussions in the collaborative notes, no hands-on exercises during the stream. 
This is in reaction to earlier feedback, that we cannot provide enough time for exercises with all new tools during the workshop. 
If you want to try things out by yourself after the workshop or type along (it will be fast!) you can find the installation instructions for the needed tools in the bottom right square in our [installation instructions](https://coderefinery.github.io/installation/). 

:::

# Day 6 - 19/09/2024

## Icebreakers
**What's the worst bug you have seen or experienced?**
- CrowdStrike update on Microsfot windows taking down all airports in Europe :) :+1:
    - Hopefully they are watching this episode today to learn about testing :+1: :simle:
- Error in the data file, used in computational code, which was untoticed for a decade. A lot of publications were made with a slightly wrong data.
- The Mars Climate Orbiter crashes because an error in units in the code.

**How do you make sure your code continues to work when collaborating with others?**
- Dependencies are well specified
- I have not collaborated with other reseachers that are capable of utilizing code independently
- I have no idea

**You just got an idea on how to change your code. But how do you make sure it continues working after the change? Any tricks you use and can share?**
- Lots of "if" and "print" :) :+1:
- Test data with recorded test results, ensure the expected results stay the same
- .

## Automated testing
https://coderefinery.github.io/testing/

## Motivation
https://coderefinery.github.io/testing/motivation/

1. How do you recommend people test your code before publications, like to make sure each line of code is doing what it is supposed to? I ask b/c sometimes, you may be the only researcher in your group who has expertise coding and is supposed to do all of it for the group (I ask just to ensure accuracy before publication)?
   - In this talk we will talk about test-driven development which means implement the tests for each function before writing the function itself. To my experience, having a module code and add "enough" tests for your functions is the way to go. Recently I started using GenAI system to add some tests too.
   - Can you explain how to use GenAI? or do you mean ChatGPT?
   - Yeah, it' a good qusetion.  I think it's hard to know and an actually interesting scientific question.  I focus on testing things where errors are most likely and not obvious (for example, I might not test reading/writing but would try to separate the main analysis to functions that can be tested with known input)

2. I mostly develop software to analyze my experiments or keep track of changes in variables in experiments, I'm not sure how I should incorporate tests when developing these software? Would it be okay to just have a simple checker for some e.g. reference samples and ensure that it gives the proper result everytime as I add new features?
   - I have the same question
   - You can check for example is the function produces the variable type you required. For example if the result is a data frame you can test if the columns are floats (numeric). Or if it has the required dimensions.
       - in my case, this is already given since it comes from a tool with standardized format, but yes, I think adding these never hurt!
   - Simple checks for reference samples seems like a good place to start!  Also can you break the hardest parts into separate functions that are easy to test, but don't worry about other low-risk parts?

3. Are there any GenAI that you can integrate into your local computer (without it being on the browser)? I ask b/c of working with private data.
    - You can use local models like Llama to run locally on your machine. Some IDEs (like Cursor.sh) have integreted adding these models to your development.
    - Ollama: https://ollama.com/library

:::info
### When is it OK not to add tests? **choose many**
- Jupyter or R Markdown notebook which produces a plot and you know by looking at the plot whether it worked?
    - ooooooooo
    - Is it not a test in itself to plot?
        - but what if you plot data and you actually do not know what to expect (in certain boundaries)?
    
- A short, “obviously correct” Python or R script which you never intend to reuse?
    - oooooo
    - Please, define "obviously correct" ;-)
    - Once I heard that someone said: go to the library and find undergrad theses, find the word "obviously" and you always find an error.
- A simple short, “obviously correct” shell script?
    - ooooooooooo
- Can you give other examples?
    - 
:::

4. How to test codes with 'random' inputs? So, the result is reproducible, but might vary in actual numbers? .
   - You could add a seed to the random generator to produce known outputs (but any small change to the method could give different output)
   - You could do statistical tests in simple cases
   - Could you force it one directon or another by making the RNG always return 0 or 1 or 0.5 and get a known result?

5. How to test a GUI code? So a user can use different actions in a different order.
   - There are ways to test GUIs, but I don't know them. Same with websites.  I think it involves labling the buttons so that clicks can be simulated, which requires consideration even in the design phase.

5. when I mainly code to do data exploration, plotting and analysis, how do I integrate automated testing? Like I don't use models and have hardly tried to write functions.
   - If it's mainly data exploration, maybe you are always looking at the output of every bit, and there aren't many "static" things that should stay the same for long times.  I might not worry about tests here either, unless I can split out some common functions which will get reused often.
   - (of course it's better to test everything, but let's be practical...)

6. Can you talk about your experience integrating Ollama on your computer? Have there been any security concerns having it locally?
   - I didn't face any issue up until now. Also it's an open-source software under heavy developement; and many of the issues are getting addressed and resolved. Usually I'm more concerned about uploading my data (or any other private/personal data) to cloud-based providers like OpenAI etc.

## Testing locally
https://coderefinery.github.io/testing/locally/

7. When you have several functions to test, can you put tour test_ in a different script, so the original one is easier to read?
   - Yes! It is the best practice to have a test folder and several test scripts inside them.
       - can you give an example how that would look like in practice?

8. Are there similar programs to pytest in R and bash?
   - same question for Fortran and C.
   - For R you have [testthat package](https://testthat.r-lib.org/)
   - and bash?

9. Sometime a code depends on some physical constants, like a speed of light. Sometime these constants are redefined by a new experiment. How to make tests for the code, if the produced numbers must be different due to this change?.
   - A good question. Sometimes you need to test something which is "dependent" on an external source. Either another part of your code or an external physical system in your example. We will cover this in the upcoming sessions (under test design) which is called mocking.
   - As a first approximation: set the constant to known value for a test (default should be the same, so an old test hopefully doesn't work.  Then you can add a new test setting it to a different value)

10. how do you verify your tests? like you introduce an error/mistake in the test and how to avoid that?
    - Usually I write the test at the same time as the code and hope that they check each other.  Of course it still can go wrong but for my purposes that's good enough.

## Automated testing
https://coderefinery.github.io/testing/continuous-integration/

11. Can they show in the demo the testthat R package briefly?
    - Unfortunately we only demo python here.
    - Any watchers know R and want to come on stream and demonstrate?

12. The concept of testing is based on understanding what is right and what is wrong. What if a code, compiled by compiler A.1001 gives one result and with version A.1002 (or on other OS) - another? Any suggestion for a strategy to handle such cases? The usual sotce for that - different rounding, etc..
    - Is it supposed to give different results for different compilers?
    - But anyway, this is definitely what makes testing a scientific challenge: you need to be able to understand what is the "correct" part that should be the same across compilers, etc. Maybe you need tolerances in the tests, to handle floating point variances?
    - But compilers might have bugs! Right?
    - Oh yes.  But if your test finds a bug in the compiler, I also consider that a win.  At least you know and can work around it.

13. A question about git, what is the difference between using `git mv` instead of only use `mv` command?
    - `mv` moves the files, but git doesn't realize it (it think a file was deleted and added).  `git mv` moves the file but also updates git's state, so that it appears to be a move
    - But `mv` followed by `git rm OLDNAME` and `git add NEWNAME` is always equivalent. (there is no extra "this file was moved" info in git, it always infers it from the contents)

14. similar programs to pytest in bash?
    - Yes but I don't know them.  The idea of pytest is very standard and there are similar things in almost every languge
    - Pytest has plugins to run shell scripts, but I don't know how will it works.
    - I see various things when I do a web search but I don't have any special knowledge - I'll let someone else comment if they know.


15. what is "lart" in ls -lart?
    - Four options to the `ls` command: `-l` is "long listing", `-a` is "all files (including hiden files that start with a `.`)", `-r` is reverse order, `-t` is "sort by time".  So list everything, long listing, newest files first.
        - thanks!
        
16. what is the "SSH: triton" in the VScode lower left corner?
    - It's a "SSH-remote" plugin for VScode.  Basically, VScode can automaticalyl connect to another computer (by the ssh service, secure shell), and run stuff there.  "triton" is the name of a HPC cluster.
        - ah, interesting, thanks! Learned something new about VScode :smile:
        - Go VSCode! :D

## Test design
https://coderefinery.github.io/testing/test-design/

17. Can you recommend a tutorial or similar for testing a data analysis (so end-to-end testing I guess?) in R? In my specific case, my data are gene sequences.
    - I see this qusetion but don't have any good answers: starting with `testthat` tutorials might be a good starting point.  Come to think of it, I don't recall any good tutorials designed for data-type workflows in any language, but there must be some...
    - There are some unit testing principles for data analysis projects based on Python that can be export to R, check [this presentation](https://www.youtube.com/watch?v=Da-FL_1i6ps)

18. Is there any tip, when testing Python code with external data (e.g. API query)? e.g. it is not always easy to predict what kind of data is fetched. e.g. sometimes, None, empty string, or strange string etc 
    - I would include some test data along with the code: tests work with that test data so it stays somewhat predictable.  Hopefully.

:::info
### Lunch break (1 hour), we resume at xx:00
:::



## Modular Code Development
https://coderefinery.github.io/modular-type-along/


**What does "modular code development" mean for you?**
- splitting code into several parts that are self-contained
- I'm not sure about this word, but I would guess that some functions or components are reused between different tools
- Divide and conquer

**What best practices can you recommend to arrive at well structured, modular code in your favourite programming language?**
- Pencil and paper first drawing the calls, parts that can be modularized, then writing empty files with only comments and what they should do there, then adding the code.
- .
- . 
  
**What do you know now about programming that you wish somebody told you earlier?**
- Create and import separate modules for functions, do not ever copy-paste from file to file
- .
- .
- 
**Do you design a new code project on paper before coding? Discuss pros and cons.**
- Not before but during planning. Would be better to do it beforehand for very complex workflows
- When and I got the ideia of a function not so clear, I usually do some notes on paper of the steps.
- At least one scheme about the main idea, and then some other while creating functions

**Do you build your code top-down (starting from the big picture) or bottom-up (starting from components)? Discuss pros and cons.**
- Bottom-up in the sense that I write the workflow linearly, function-by-function
- 
- .
- 
**Would you prefer your code to be 2x slower if it was easier to read and understand?**
- Depends of how it scales: for high-throughput datasets, absolutely not :+1: 
- Yes! I often end up working with code that was put up several years earlier by me or others.
- Absolutely, I ain't in a rush :)
- yes, but see the first answer (not for high-throughput datasets)



19. Where is the music from?
    - The music is written by a CodeRefinery member - specially made for us :-)
    - Wow that is very cool. I will miss the music.

## Our task
https://coderefinery.github.io/modular-type-along/lesson/

20. To the audience: how is this not modular?
    - If you change the data, you either have to modify it on the code, or copy it again with the modification

21. So modular code development follows the Don't repeat yourself principle.
    - Yes - that's a good starting point!

22. You may need an underscore in outfile.
    - thanks!

23. Is the for loop now going through the first 25, first 100 and first 500 rows of data?
    - Yes.  Because of the existing structure it re-reads data each time.
        - thanks! I guess, then a first question to the data should be how long it is (how many measurements exist/how many rows of data there are)?

24. I'd like to use if out_file is not None instead of if out_file. In addition to None, also False and 0 evaluate to not True in python.
    - .

25. where do you specify in_file? how does the code know where is the data?
    - get_data("temperatures.csv", num_measurements) is the specifications
        - ah, so def ... is a function and then later in the for loop you give the file. sorry, used to R, not so much to Python

26. I think we can remove out_file argument  in `plot_temperature`by defining after `if out_file:` `outfile = f"{len(temperature.index).png"` :+1:
    - If we reuse the function for something different, maybe we need to specify other things within the filename?

27. Maybe it's better to put get_mean() function call inside plot_temperatures() instead?
    - .

28. Why not use statistics.mean instead of creating a custom function?
    - I agree 
    - In fact, the mean could be calculated directly in the plot_temperatures function instead of being a function argument

29. Is there a common format for function names and variable names? I think I would not immediately understand the difference between get_mean (a function) and num_measurements (a variable) if I would not see the function definitions in the same script.
    - I'm not one of the instructors, but please see: https://docs.python-guide.org/writing/style/

30. We can also test if the column Air temperature is numeric. I experienced errors where the simple statistics are not calcualted because, pandas read it as object (because of some missing values)
    - Good idea.  This could be a test but also it would be good to test each time the data is read.

31. Maybe for the command line we define the out_file too?.
    - Oh yes we should do this.
        - Ooh, I didn't realize it should give a window with the plot, ah right there's `plt.show()`

32. You would need to disconnect the num_measurements from the loop and give the out_file from sys.argv of argparse.
    - yes, thanks!  We are on it.

33. Isn't in_file an argument not an option?
    - Is it @click.option() to do that?
    - I think it's like this for arguments: https://click.palletsprojects.com/en/8.1.x/arguments/

34. I would love if someone could translate the demo code (in the documentation, https://coderefinery.github.io/modular-type-along/solution/) to R! :+1:
    - Let's create an issue on GitHub :+1:
        - I checked, there is an issue already (#31): https://github.com/coderefinery/modular-type-along/issues/31

35. What advantages are there to using click instead of argparse?
    - It's more modern/easier to use.  But a separate module so I usually use argparse. Really, either one is mature and stable enough to be good.
        - Modern / easier in which sense?
        - argparse has a lot of boilerplate code somewhere in the file.  Click has everything defined right above the function, where it's easy to see and know what it does.
            - Would you say it's also a matter of taste? I like my argparser in the beginning of the file, listing all the arguments in one place.
            - Definitely a matter of taste if you ask me.

36. This was fun! kudos!
    - yes, thanks! AND: please add this in R as well!
    - If you know anyowhe who likes R who would like to donate the solution, we can help integrate it.  I know someone to ask though...



:::info
### Break, we resume at xx:04
Continue suggesting what we should do next.  You can vote below:
- add tests: ooo
- make jupyter import these functions: 
- git repository: 
- split script functions into another module: o
:::

37. Why did we need the .gitignore file?
    - Without the `.gitignore` we get a lot of files listed when we do `git status`. This is temporary files and generated files. These files we don't want to version control. We list these files in `.gitignore` and consequently git will not list these files during `git status`. Less clutter so to speak.

38. If the data is complex (many possible variations for input values), then the testing code would become quite big and difficult for readability etc. Is there a good solution? (e.g. is it a good idea to store the test data in another file and the test code read from it?)
    - Yes exactly.  Often I would make a testdata directory for this purpose.

39. Are there any (good) AI tools which can automatically generate a test code, based on the existing code? (Thinking of test code seems to be not simple sometimes) Links to the tools would be great to share!
    - .

40. For Aalto people, we can get credits but need to submit the exercise to an e-mail address, will we be given the address to send this PDF file? Sorry if I missed the info somewhere.:+1:
    - email:support@coderefinery.org

## Outro
https://github.com/coderefinery/workshop-outro/blob/master/README.md

## Feedback

Today was:
- too fast: 
- too slow: 
- right speed: ooooooo
- too advanced: o
- too basic: oo
- right level: ooooo
- needed more exercise time: o
- needed less exercise time: 
- I will use what I learned today: ooooooo
- I would recommend today to others: ooooo
- I would not recommend today to others: 
- too slow sometimes, too fast other times: 

One good thing about today:
- I didn't knew click, that was nice. :+1::+1:
- I have been using modular coding but this overview was a nice touch :+1:
- ..

One thing to improve for next time:
- ..
- ..
- ..

Any other feedback?
- Thank you for the course, I learned a lot! :clap::clap::clap::clap::clap::clap:
- Perhaps think about lunchtime for different timezone? ECT is one hour late, I think
- ..



