+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 5"
+++

# Day 5 - 18/09/2024

## Icebreakers
**How would you explain your current job to someone in the year 1700? (if you don't know, write what you do and we'll try to figure out!)**
- "I am an alchemist." :smile: 
- I'm watching clouds
- Automatic librarian?
- I use machines that contain parts that are smaller than the eye can see. I use these machines to collect information and sort it in different ways.
- I guess something like being a munk (I study paleoenvironment, so maybe "gods creation" would be understood :D)
- a witch? :smile: a person that takes care of nature, actually a cartographer as a profession
- a weather fortuneteller

**What's the best documented project you've seen?**
- I am still looking for a well documented project.
- I like the tidyverse packages (R)
- Matplotlib and pandas have nice documentation.

**Do you prefer reading short social media posts or long blogs? How about short code snippets or long source codes?**
short social media posts: o
long blogs: oooo
short code snippets: oooooo
long source code: 
both short (professional) social media posts and long blogs (different goal):oo


## Questions from day 4

1. For the conda environment, is it recommended to use these for R scripts as well (i.e., the YAML file), and to post this on GitHub with your script so people can set up the environment and then copy your script, or is it recommended to use CRAN or Bioconductor?
    - I would recommend the first, use the YAML file to list the dependencies and channels, and version control this files such that it is part of your GitHub repository. Then it is available for other people to copy/reuse.

2. Can you clarify how dependencies and channels are related? I am a bit unclear about the difference.
    - Here is snippet of the YAML file that creates the coderefinery Conda environment:
    ```sh
    name: coderefinery
    channels:
    - conda-forge
    - defaults
    - bioconda
    dependencies:
    - python>=3.10
    - click=8.1.7
    - ipywidgets=8.1.2
    - jupyterlab=4.1.2
    ```
    The channels are the places where conda will search for packages. Here we have 3 channels. The packages that will be searched for and installed are listed under `dependencies`. The dependencies are the software being installed.

3. If packages are the highest level, containing metadata, data, and functions, and loading the library creates the environment and contains all the functions in that package?
    - in Python `import SOMENAME` basically runs `SOMENAME.py` or `SOMENAME/__init__.py` and makes all of those available via `SOMENAME.*` - was that the question?
    - I meant in R?

4. ~/Library/Caches/org.R-project.R/R/renv/cache/v5/macos/R-4.4/aarch64-apple-darwin20 --> apparently I had tried to do renv::init() in R but it said there was already an renv in my home directory (see above), how/when are these created and can you have more than one, just in dif subfolders? I am not sure I fully understand this workflow: renv::init(), renv::snapshot() and renv::restore().
   - Can someone who knows R more answer this?

5. Can you explain the idea of .gitignore?
    - The purpose of .gitignore is to list files or subdirectories that you don't want to be version controlled. Here is the content of a .gitignore from a repository in CodeRefinery:
    ```sh
    *~
    public/
    static/processed_images/
    ```
    This states that any temporary emacs files, these are named `anytext.txt~`, should not be version controlled. Likewise, any files under the subdirectory `public` and `static/processed_images`. Git will not care about files created in these subdirectories.

6. Are lock files typically in .json formats?
   - `renv.lock` files are in json format, https://rstudio.github.io/renv/articles/renv.html. But other lock files don't have to be in json format.

7. You mentioned new types of publications that are more common now for tool development -- do they require less strict peer review? How does this relate to TENK Finland?
   - They still have peer review, and I guess the strictness depends on what venue it is.  Most are designed to be useful, as in not excessively gatekeep, I think.
   - Some of us have actually been working to pressure JUFO in Finland to rate the Journal of Open Source Software higher.  But this is basically a opinion-based decision done by entrenched academics who are benefited by the current system, so it's slow going.

8. It seems there are several markdown languages, like YAML, XAML, XML -- which are slightly different - what is the difference, which is used for a CFF file, and how do I generate a CFF file easily for my software I developed?
   - I think CFF is YAML, and there seems to be a builder here: https://citation-file-format.github.io/#/create-a-citationcff-file-now

9. Have any of you gone through the trademark process for any tool you have designed in the Nordics -- what was that process like, outlined from start to getting the trademark (pre v. post-publication)?
   - I don't know anyone who has.  It's never been close to relevant for us.

10. How do we know that: Lines 11-12: The compiler gcc and the library libgomp1 will have evolved (based on the name libgomp1)?
    - From exercise Containers-1: https://coderefinery.github.io/reproducible-research/exercises/#recording-environments
    - We don't "know" but this is a general progression: the gcc compiler gets new versions and new features every few years
    - However in this exercise, this isn't what I am most worrid about: compilers are very basic tools so they try very very hard to not change them and break old code under any circumstances.  And `libgomp1` has this `1` on the end, which is the "soname" which serves as a version: I think the convention is that anytime a library gets incompatible changes, that number should increment.  C programmers are much more careful about backwards compatability than others.

11. Why am I getting this error when trying to run snakemake? snakemake -j 1
            Traceback (most recent call last):
          ```
          File “/../../../../../../word-count/code/count.py", line 2, in <module>
            import click
        ModuleNotFoundError: No module named 'click'

        Error in rule count_words:
            jobid: 4
            input: code/count.py, data/last.txt
            output: statistics/last.data
            shell:
                python code/count.py data/last.txt > statistics/last.data
                (one of the commands exited with non-zero exit code; note that snakemake uses bash strict mode!)

        Removing output files of failed job count_words since they might be corrupted:
        statistics/last.data
        Shutting down, this might take some time.
        Exiting because a job execution failed. Look above for error message
        Complete log: .snakemake/log/2024-09-17_Number_ID.snakemake.log
        WorkflowError:
        At least one job did not complete successfully.
        ```
    - Have you installed the coderefinery Conda environment? It contains the module click(click=8.1.7), but it seems that your python environment is missing that module. The way to create a python environment named `coderefinery` with conda is:
    ```
    conda env create -f https://raw.githubusercontent.com/coderefinery/software/main/environment.yml
    # To activate the environment:
    conda activate coderefinery
    ```
    I had installed it but may have not activated it in that window.. i might have deactivated it at some point, need to check

# How to document your research software
https://coderefinery.github.io/documentation/



:::info
## Why documenting code?

- To make it possible for other people to use the code
- To know what it is doing, what is needed, what are its output. Needs to be sufficiently clear to be able to tweak it as needed.
- So that it's usable.  What's the point if it's not? (the level depends on the code)
- To remind myself of the functions I did. It's like having frozen food in the freezer. If its not labeled, I have a hard time to know what it is.  o
- To prevent having to rewrite parts of the code that are not understandable later
- to explain to myself and others what the code is supposed to do and why in other words than "code"
- People in research group settings do not have the same skill levels when using different analysis tools. Well documented code shared for common use improves research integrity and reproducibility. By the way, "well documented" means very different things for different audiences: someone might want function-level parameter types and someone else may want to know in plain English what a specific tool does and why. My solution was a pdf explaining the contents and usage instruction for tools in a toolkit I made for the research group.

:::


:::info
## Create a wishlist

- A detailed way of using the code, input/output format, command lines and potentially some few examples of how it is used. Of course, what are all the parameters and all these minutia that would allow to use the code to its full.
- What are the assumptions hidden "under the hood", especially in the case of research software
- Where is the code, how to use it, what does it do and not do, towards what purpose should it be used, are there any dependencies
- examples on how to use the software/package/library
- a gallery with examples (some of them are easy and quick to be understood by an image)
- It has several levels: at first just quick examples of using it, with the most often used arguments. Later, probably a "proper" documentation with a list of all arguments and their default values, and a list of outputs, assumptions inside, and always examples, examples, and examples
- A short snippet at the top with input (and options/parameters), output, what it does, anything I should be aware (full paths etc), requirements (and obscure details, e.g. only version of a library that works). Comment throught on what does what (and why, if not obvious)
- Easy to find (I want basic info in the readme in an obvious place)
- A document with all the libraries and versions
- flowcharts for working with the library
- getting paid to do the extra work :+1: 
- Am I allowed to use it (licensing)? :+1:
:::

## Popular tools and solutions
https://coderefinery.github.io/documentation/tools/



12. In code documentation: "Can be used to auto-generate documentation for functions/classes" How? Do the comments have to be a certain format? which tools offer auto generated documentation?
    - Yes, comments need to be in a format that can be read.  This is called "api docs" and many tools made for documentation have some implementation of this. Both Doxygen and Sphinx offer this.
        - thanks, can you recommend any ressource for total newbys (mainly using R) ?
            - For R there is a tool called `roxygen2`, https://roxygen2.r-lib.org, but I have no experience with it.

## In-code documentation




::: info
## Comments: Which one is more useful

Comment A:

Comment B: ooooooooooooooo

Why?

- It explains what the funtion does
- B explains the **why**:+1::+1::+1::+1:
- it does not only reproduce the code in plain languange, but gives a reason
- The first one doesnt describe what the code does

:::


13. Are these docstrings related to the "api docs" (see question 12)?
    - Yes, the can be.  Most of the API docs things will automatically read all docstrings and compile it into a organized reference.

14. Did you write the Python docstring entirely by yourself or is it also programmatically created?
    - In this lesson or in general?  In this lesson we probably wrote them all ourselves.
        - I'm asking because I use python extensively and have not thought about if there is a way to create the docstrings programmatically.
            - Some IDEs create the docstring template automatically, but you need to add detailed information.
                - Thanks, that clarifies things! Great.

## Writing good README files
https://coderefinery.github.io/documentation/writing-readme-files/

15. could you explain why one wants to use badges?
    - If you get an Digital Object Identifier (DOI) from a place like Zenodo for your software, you can add the DOI as badge to your repository.
    - In general when you want some important information to be displayed in a way that is immediate to read to someone that views your repository in github/gitlab/other git forges (Note that these badges typically are links to something that lives on the internet)
        - ok, thanks for the clarification to both!

:::info
### Break, we resume at xx:11
:::

## Sphinx and Markdown
https://coderefinery.github.io/documentation/sphinx/
Mainly a demonstration of using these tools on Github Pages.  The idea is reusable to other tools too.  This is a long demo.


16. When creating a package, in what folder should I start sphynk? Inside doc or it has to have a separate folder?
    - If it's being included as part of some other software, that has the code there?  Often `doc/` at the top level but you see various things. :+1:

17. Is there a specific document generator that is used for PyPI?
    - It uses whatever readme file there is (but you need to tell it where it is / to use it).  It can use markdown, ReST, and maybe(?) others.  This is defined as part of the package metadata (pyproject.toml or setup.py)

18. Why would you want to use Sphinx or a wiki page rather than just a README file in GitHub?
    - A README is a good starting point anyway.  You'd think about these once the project gets so big it's not enough (like below, full API docs are a bit too much for README files).
    - Also Sphinx has plugins for API reference generation, which a README alone does not give you. 

19. How is building a static webpage using sphinx (or another tool) beneficial compared to just build a HTML static webpage directly?
    - Like writing raw HTML?
        - yes
    - If you want to write raw HTML, you can, but with things like Markdown it's a lot higher level: focus on the content and not the presentation details.  It's a trade-off most people like it seems.
    - Markdown is basically fancy syntax for the most common HTML tags (you can embed raw HTML even).
        - thanks!

20. In MyST markdown this should be equivalent to:

    ```
    :::{automodule} example
    :members: 
    
    :::
    ```
    or something like that.  I'll test.
    - Thanks for testing, I hav'nt been able to yet
    - I'm not sure if it needs `true` there but we'll see.
    - ~~great! it works~~.
    - Actually, it does not work like that. However there is another extension called `sphinx-autodoc2` which has a similar syntax. <https://myst-parser.readthedocs.io/en/latest/syntax/code_and_apis.html#sphinx-autodoc2>

21. I'm a little unclear what an action is on GitHub.
    - We'll see more about it tomorrow, but basically: every time you push, it will automatically run some stuff for you.  This is really cool!
    - Today, we see it being used to build a webpage (and we hook it in so that it makes it available on "Github Pages")
    - Tomorrow it will run automatic tests and warn us if the tests don't pass.

22. I am thinking this might be handy to build a personal webpage as in "about me" or a short bio - anyone has done that and can recommend a tool/pathway to do that?
    - Yes!  Many people do this.  If your github username is USERNAME then a repository named `USERNAME.github.io` will be available at `https://USERNAME.github.io/`.  There are different tools to do this, "jekyll" was a built-in one but I'd recommend searching "personal github pages webpage" and see what is good these days

23. Does Sphinx work with GitLab?
    - In theory yes: Gitlab supports runners that can run code automatically and do things.
    - Another question is: does Gitlab provide free action runners?
    - Gitlab does support actions (called pipelines I think?), but you may need to get your own runners to do the execution.
    - Does anyone know the current state?

24. How do you connect or link the Sphinx documentation in your repo to your code in your repo on GitHub?
    - Hm... I'm not sure what you mean.  They can be in the same repo, so at least they are findable from each other
    - Then, via things like autodoc/API docs, if the builder can import your module, then it finds it and documents it (and can link to the source automatically).
    - There are other ways to tell Sphinx where the source to the docs are and automatically like there.
    - It really depends on what you mean by linking.
    - I meant your first bullet point, thank you. +1


## Summary
https://coderefinery.github.io/documentation/summary/

:::info
### Lunch break (1 hour), we resume at xx:00
:::

## Jupyter
https://coderefinery.github.io/jupyter/
We'll see some of the basics of Jupyter, but that's not the main message: we see how things like version control are still useful with notebooks (in whatever system you use), and how they can be archived and shared easily (which are also points for other systems like Rmarkdown notebooks and so on).


25. On the choice of VS code vs Jupyter lab - availability and actual function of extensions can be a factor. Not all extensions work with VS code as far as i can tell.
    - Jupyter lab is for litterate programming, where you want to mix code, text and figures. It is for sharing your ideas, concepts with others. VS Code is a programming editor. If your focus on producing most code, I would choose VS Code.
    - I was mostly evaluating them for notebook use.

26. Yes Jupyter came from "julia, python, and R".
    - a new name whes split from "IPython Notebook" which was part of the IPython interperter

27. Anyone has experience or can compare Rstudio (Posit now) and then Rmarkdown or Quarto with Jupyter? I mainly work in R. Or VScode to write Rmarkdown/Quarto/Jupyter?
    - I think RMarkdown is very close to Jupyter. I prefer to work it in RStudio to get the most advantage with keyboard shortcuts, and the exportation to presentation, reports, and webpages. And when you want to get fancy you can even use the templates (when export it).
        - like Rmarkdown templates?
            - Yeah, like the tufte template.

28. Does anyone have much experience editing Jupyter notebooks (or others) from VS Code?
    - You need to install an extension, but yes, possible, and nice.

29. .A stupid question about notebook. Can I execute a command (eg ls) on the computer which runs the browser with notebook, and on a computer, which runs as server?
    - No, I don't think so.  All commands get sent to the remote server (running the jupyter server) for executaion and browsers generally prohibit web pages from doing stuff on your local computer (would be a big security problem).
    - When using a server, Jupyter typically runs in a container, but you may have the possiblilty of accessing files in different folders. Depends how it's set up.
    - Actually, if you use "%" before the command, (i.e. %ls), it will execute it.


30. Is there such a thing as binder for Rmarkdown or Quarto documents?
    - It seems like you can configure Binder to start Quarto: https://quarto.org/docs/projects/binder.html
    - Basically Binder installs stuff from defined files, and then starts some URL.  With a bit of configuration you can tell it to install what you need, and then direct to the right link
    - For R projects see [holepunch](https://github.com/karthik/holepunch)
        - great link, thank you!

31. is Binder open and free? who owns the infrastructure?
    - it's free. From what I remember Binder was a publicly fundend project at first.  The software is open source and they rely on donations (mostly from cloud providers I think) for the cloud credits that let it run.  (this was several years ago, they may have a more stable funding source now)

32. When you write your scripts in a notebook - is there a good solution to run the code in the terminal?
    - you can run as a script or you can include the content of the script as cells, we;ll show. you can also run scripts in a Jupyter notebook cell using shell commands. see "!" in https://coderefinery.github.io/jupyter/extra-features/
        - thanks! and how about a Rmarkdown or Quarto notebook?

33. What is "localhost:8888/lab"?
    - 'localhost' is a network name for "your own computer".  :8888 is the "port" (identifier for what service is running locally).  So it tells us that it's connecting to your own computer to access the JupyterLab (which the instructor started in another window - it said this address for connecting)
        - Great answer, thank you! :)
        
34. so is the instructor now running jupyter or binder? and on their own machine?
    - The instructor started jupyter lab in the terminal on his machine. He is running jupyter locally and not on Binder.
    - If it was binder the URL in the browser ways say "mybinder.org" somewhere in it.  "localhost" usually would mean "somehow on your computer".
        - :+1:

35. The type of cell is Code
    - It's a code cell,
    - should be a markdown instead
      - Yes. Thank you both.


36. sorry, you are a bit fast for me. How do I distinguish a markdown text from a code cell in the jupyter notebook?
    - Above towards the top of the notebook frame you see a "Code" text - this selects the type
    - (in practice I try to run and if it does the wrong thing, I change the type)
    - Also, the cell that has in the left side `[ ]` is a **code cell**. Markdown or text cell does not have it. +1 better!

38. I get 3.104 😅
    - Heh, nice!  If you increase the number of points does it become more accurate?
        - it does! how do I run "every code cell after this"?
    - I don't have it open but is there a option in the "Run" menu?  (in practice I shift-Enter multiple times until I get to the point I want)
        - ah,ok, yes there is a option "Run Selected Cell and All Below"

## Notebooks and version control
https://coderefinery.github.io/jupyter/version-control/

39. Does jupyter only come as a browser window? Or does it have a desktop app as well?
    - The "Jupyter server" basically is a browser-based thing.  But it is also the format, and for example VS Code and open, edit, and run them (I havent' done this but it's referenced abvoe)
    - There is a desktop app here: https://github.com/jupyterlab/jupyterlab-desktop - I haven't used it, and I think it is basically one of these "embed a browser in an application" thing.
        - so it is roughly equivalent to Rstudio/Posit desktop and Rstudio server? And then its just a question of preference or main language?

40. I think I've lost one step. In my JupiterLab there isn't this connection to github repo. 
    - It might need a git extension set up.  Let me check.
    - That might be it, thanks. 
    - jupyterlab-git, with conda/mamba I think it automatically initializes, not sure if the Pip one does
    - I'll look it up.

41. Sorry, I missed where is the original git repository, could you please tell me its address?
    - Did they use the current example and initialize a new git repo as part of the exercise?
        - May be, but then how do I compare with their changes? Or should I make the changes and compare internally?
        - we showed an example on the local computer and one on GitHub: https://github.com/coderefinery/jupyter/compare/5ff55b8..fce21e6
            - Got it, thanks

42. what was nbdime?
    - "NoteBook DIff and MErge" - basically the basic tool that does these pretty diffs (and merges) of notebook files, that are too complex to use the standard "git diff" commands on
        - aah. thanks!
    - It can be hooked into git, Jupyter, and so on.

:::info
### Break, we resume at xx:05
:::

## Sharing notebooks
https://coderefinery.github.io/jupyter/sharing/

43. is it recommended to include extensive datasets? Or would you rather include a "example" subset of your data? but then its not fully reproducible
    - I'd include a small example for testing and then a link to the dataset in a good repository (like we saw yesterday).  It could even include some automatic-downloading stuff (but I'd make sure it's obvious how to add your own data - doing downloading automatically can make it hard to understand)
    - You are very right about the reproducibility trade-off, though.  There's not much to be done when the data is big, but it's something to consider.

44. Under what use case would you want to use Binders than to just keep your Jupter notebook in GitHub?
    - If you have a simple ( not too computationally expensive ) show case, where you want to provide users with the ability not to install jupyter and still run it. 
    - would they need to install Jupyter if you had it in GitHub?
    - They are for different use cases: Github/lab/etc is for storing code and developing it (and has preview so you can see it but not interact).  Binder allows someone to run easily if they just want to test.  Local install would be for serious development work.
    - So they can run it on the Binder browser?
        - yes
        - Got it, and there is no other online platform where you can do this, just Binder?
    - There probably are some.  Working without a login like Binder for short-term experimentation, I'm not sure.
    - Okay thank you.

45. .Is it possible to include in the requirements.txt some python libs that are local files and run it in binder?
    - No, Binder cannot access your local computer. You can reference files in the GitHub repository. We saw some examples of that yesterday in the environment.yaml files.
    - Do you mean in the repository itself? 
        - sorry, yes, I meant in the repository

46. Are there any other tutorials for jupyter-git and binder that you would recommend? to explore more than we covered today

47. following up on 46: tutorial for Rmarkdown/Quarto -> Binder

## Feedback

:::info
### News for day 19.09
- Today we did the things in the lesson
- Tomorrow will be automated testing and modular code development. We will continue to do demonstrations, nothing to install
    - These lessons are really the capstone of the whole course and you see everything we did in action again.
:::

Today was:
- too fast: oo
- too slow: 
- right speed: ooo
- too advanced:o
- too basic:
- right level: oo
- needed more exercise time: oo
- needed less exercise time: 
- I will use what I learned today: ooo
- I would recommend today to others: ooo
- I would not recommend today to others: 
- too slow sometimes, too fast other times: 

One good thing about today:
- Sphynx and Binder are tools new to me. :+1:
- Jupyter is a new tool for me
- NBdime was new for me, never had a chance to see/use it
- ..

One thing to improve for next time:
- R examples would be nice. :+1::+1:
    - thanks for the feedback, good suggestion
- more practice/interactive exercises would be great :+1:
    - indeed, exercises are a better method for assimilating the material; demos are a way for us to know that everyone can follow, but it is not ideal 

Any other feedback?
- ..
- ..
- ..


