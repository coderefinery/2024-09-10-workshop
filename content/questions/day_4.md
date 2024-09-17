+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 4"
+++

# Day 4 - 17/09/2024

## Icebreakers

Let's test the notes with some icebreakers! :icecream: 

**Have you heard the sentence "hmm... works on my computer"? What does this mean in practice? How do you solve this problem?**

- maybe it means a difference in the environment or operating system? :+1: :+1:
- I have heard and said it...
- Use docker or other containers
- I think "my stuff isn't installable enough" and think about how to make it so.  But I think this is missing a lot of parts of it... :+1: 
- By creating a commonly used toolkit in Puhti, where everyone has the same base installations
- .. 


**What are your experiences re-running or adjusting a script or a figure you created few months ago?**
- It often feels as if I have to think through everything again, particularly if the choice of variable names is cryptic at best… And it might be also that some of the paths are no longer valid, because I've cleaned my folders.
- It's easy only with scripts and workflows that were thoroughly documented and logged (I had to re-run all analyses for one manuscript 8 times. 8!) :+1:
- Sometimes I have issue with packages I used that don't work with the newer version of the software I use (e.g. R). 
- It is never how I remember, and because I have a habit of "poor" commenting, it always take a while.
- For others I see, "I have to do revisions" is the worst part of their work.  It hardly ever goes well.
- I allways have a problem, because I'm allways lazy to document or even to comment my scripts.
- when I start analysing data I often try out different things and it all gets messy very fast - so later I cannot find what I did in the end because there are many dead ends.

**Have you continued working from a previous student's
script/code/plot/notebook? What were the biggest challenges?**
- Not from a previous student, but there are the usual instances of old published software/codes, particularly those written in Python 2 that need to be "converted" if one wants to use Python 3.
- Having to update the code so they are more readable / straight forward because I got better in the meantime and change my way of coding things
- Complete lack of documentation and any explanation of what anything does and why, and why specific QC decisions were made. :+1: :+1:
- To understand why it works or not :) :+1:
- Sometimes it was easier to just rewrite the code again (including code from myself) - I agree it's often what I end up doing too.
- It "doesn't work" in any way I can figure out.  When I first started research I was warned against every trying to resume old projects, always start new with something small enough you can re-do.


## Questions for the session

1. https://www.kth.se/form/build-systems-course-and-hackathon-part-i --> what are the prereqs for this course?
    - Ideally you have access to an HPC cluster. The participating clusters are Dardel (KTH), CSC Puhti and Mahti (all Finland), Triton (Aalto), and many more. Which affiliation do you have?
    - Uni of Helsinki
    - I meant are there technical prereqs?

2. "Two" is rather quiet.
   - Is it better now?

## Introduction
Summary:
- This week is less hands-on, since it's harder to make exercises that can be done in a reasonable time, and many exercises are more specialized.
- Instead, we spend more time in demo and discussions and you can work on the exercises on your own time.
- You can get help with the exercises at the "bringy our own code sections", or your colleagues, or local support.


## Reproducible research

*Intro*
https://coderefinery.github.io/reproducible-research/
*Motivation*
https://coderefinery.github.io/reproducible-research/motivation/

3. How many people here have failed to reproduce a (computational) experiment?
   - Several times with Molecular Dynamics simulations.
   - Classic neuroscience paper about same version of software giving different results in different operating systems: https://pubmed.ncbi.nlm.nih.gov/22675527/
   - It sounds like this happens all the time even pre-publication.  I wonder how much of "I have to work this weekend" is "my results changed and I have to figure it out"

4. Will we review snakemake?
   - Snakemake will be demonstrated, yes.

## Organizing your projects
https://coderefinery.github.io/reproducible-research/organizing-projects/

5. regarding "everything in one folder" - my raw data is gigantic and I work on it in the first place on a server to crunch it down - then I put the output of that onto my local computer. So it becomes already two folders in two different places. Do you have a recommendation for that?
   - I think this is fine, as long as the links/relationships are well-defined.  My suggestion (I'm not quite sure how to say this) is that each unique "thing" (1: big raw data, 2: working code and data) has its unique folder name and carefully tracked itself.  In working code it needs one variable inserted: path to the big raw data.

6. Expanding on the question above. In the manuscript phase, when the data are in a different place (say, CSC Puhti), and people are working on the manuscript in a shared workspace, how can you keep the links/relationships sane?
   - Working on the text itself <- yes
   - multiple people editing the same files is really hard: either people have to edit at different times, or use version control (like we did in week 1!), or constantly synced servivce like Overleaf/Google Docs/etc.

7. Is there a good way to catalog how the "external" data is obtained other than a README note? Often that information can be lost - or not clear to a new person.
   - If the data has a persintent ID (for example Zenodo DOI) that can be included.  There could be setup scripts to automatically download it.  DOIs and data repos are so recommended just because it provides a way to strictly define where and what the data is
   - We shouldn't forget one needs to know where to put the data locally, in order to work with the code

8. In which folder would you then put "intermediate results"? such as data exploration plots (masses of those) that you just produce to screen the data but never really work on later?
   - I use a different filesystem for those (scratch), but in general it is up to you. Sometimes it is "nice" to keep intermediate results if it took many days of computing.
   - I might make a `scratch/` or `processed/` dir - in same place as I'm working if it's small enough, or elsewhere and link it if it's very big.
    - 

9. Just a comment on the project structure: Something similar is available on https://cookiecutter-data-science.drivendata.org :+1: :+1: 
   - Cool! :+1: 

10. Will this course review going over how to build a GUI from a script?
    - Unfortunately no, all the covered materials could be find here: https://coderefinery.github.io/2024-09-10-workshop/
    - Do you have a recommendation for any workshops that do this?
 
- moved two questions here further down (19. and 20.)
 

:::info

**How do you collaborate on writing academic papers?**
- Overleaf or similar online tool.


**Are you using version control for academic papers?**
- Yes: oooooo
- No: ooooooo


**How do you handle collaborative issues e.g. conflicting changes?**
- One author is responsible for merging everything. It's not a great solution.
- Senior author takes decision
- First author takes decision (also because this person is the only one using verison control/ is used to the collaborative writing e.g. overleaf)
- Conflict is resolved by discussion on slack or other chat channels. 
- 

:::

10. for git for papers: is it that code has to always be consistent in order to compile run.  Thus async and pull requests is OK.  A paper text doesn't, so synchronous editing is OK (as long as someone checks it at the end)?
    - Yes with synchronous editing tools (e.g. Google docs, Overleaf) you might not want to take many snapshots, but then when you reach a new version maybe you want to git commit it. (Disclaimer: I do not like to use git for papers) 

11. I find it easy to send it to my supervisor, and he can "check" it and I get back the checked version. :+1:
    - Yes, most of the time this is "good enough" and "good enough" is the best practice :)

## Recording computational steps
https://coderefinery.github.io/reproducible-research/workflow-management/

12. Is there an alternative to snakemake for R code?
    - I am not sure, but I like to create R scripts which work as command line scripts, so with that in mind you can run R scripts within snakemake. 
        - I did a quick search and it seems that this is what they did here https://github.com/fritzbayer/snakemake-with-R
    - Here is a reproducible workflow for Snakemake and R:https://github.com/lachlandeer/snakemake-econ-r

13. How is this different from a loop? How is snakemake helps reproducability in case there is added files...etc later?
    - A loop in a script is always executed independent of whether the results are up to date or not. With snakemake only the necessary steps to update the results are taken. If you add more data files, like more books in the current example, snakemake will execute the statistics for the add files and update the results files.
        - I'm sorry but i still dont get it. Is it making the workflow easier with only executing the command on the newly added files, or is it helping somehow to make the code reproducable by running it on a state that happend on lets say: last year: september 17, and reproducing that?
            - Snakemake creates a dependency graph. It knows what a result file is dependent upon, which original files so to say. When a result file is out of date. That is the result file is older than the original file, snakemake will remake the result, execute the steps needed to update the result file. If all result files are younger than the original files no steps are taken. You cannot get back to a state dependent on date. It that case you will need to use version control where you checkout the version from a certain date and run snakemake to achieve the state.

14. How does Snakemake make the parallellization happen? Does it require the user to set some parameters?
    - Given the -j parameter checks the numer of workers (= how many cpus you can access). On HPC systems there are integration with snakemake and "slurm" (slurm is the tool to manage the queue of HPC systems.) <- That's amazing, thanks!

15. When I should better use snakemake? At the beginning of the project, during the developing of the project or at the end?
    - Not at the end I would say. If you know that the project is going to repeat the same pipeline for many different types of inputs, then snakemake or other tools for repeating the same steps with differnet inputs.

16. Is there an alternative to snakemake for matlab?
    - Matlab functions/scripts can be run in a non-graphical way, so similarly as per question 12, you can turn your matlab steps into command line scripts and then include those into snakemake steps. I am unsure if there is already an example of this way of doing things. Also: there might be some matlab toolbox that would not require you to go to the command line.

17. On my machine at least, the twitch window shows an interesting phenomenon. The image keeps getting out of focus to the point of the text becoming too blurred to read, which then corrects it self, and again repeats
    - It is the bandwidth optimisation (tries to save your internet data). In the settings instead of "auto" set the resolution to a fixed value. Sorry we forgot to mention this at the beginning.

18. Is it possible to get a page width view because the text gets quite small in the full page view?
    - do you mean popout view? (options wheel - popout player)
    - I don't see what you mean ... The twitch stream is in the browser window and the text page takes all the length but only 40% of the space centered horizontally. This way the text size gets very small.
 

19. (11.) Can you give another example of when you want to use Snakemake -- do you always need to break your script into several smaller ones e.g., tables, plotting, etc., or can you provide another usecase?
    - I think it is up to you. E.g. when working with medical imaging data, you have one dataset per subject, and for each subject I might want to do preprocessing, quality control plots, etc. It can all be in a single script that has calls to other scripts that snakemake does not "see".

20. (12.) What about sipler tools as scki-learn pipeline. Is that usefull in some situation?
    - I am not familiar with that, but sure why not? There are many tools and hopefully you can find which ones are useful for your case / popular in your field. Take this day as an opportunity for exploring these. :)


    ## Recording dependencies
    https://coderefinery.github.io/reproducible-research/dependencies/

21. I don't have experience, but have touched, using conda or renv. My first thought was: oh, this will fill up my harddrive very quickly because I will have to install and re-install all these packages again and again for every single project. And also it took ages to install all the packages in the renv. I stopped at that point. What is your experience with that?
    - I have experienced that installing packages can take time, but that was on a cluster. I on my local computer both conda and pip has been fast. 
    - I think it is the tradeoff between keeping projects separated with different software dependencies vs saving disk space and just use a "base" installation for all projects. Ideally we only work on one project at a time, but yeah we know it's never like that. :) 






:::info
**Dependencies-1: Time-capsule of dependencies**
https://coderefinery.github.io/reproducible-research/dependencies/#demo

A:
- Reproducible: o
- Not Reproducilble: ooooooooooooooooo
- Issues:
  - library names can be ambiguous. Also versions missing.
  - Need to read carefull and pick up libraries in the run 
  - Module version numbers missing. Not possible to reproduce.

B:
- Reproducible:
- Not Reproducilble: oooooooo0oooo
- Issues:
  - Versions are missing. There might be conflicts in versions. 

C:
- Reproducible:
- Not Reproducilble: oooooooooo
- Issues:
  - Version information is missing. 
  - I don't understand what this file is supposed to tell me
  - Git project commit version is missing.

D:
- Reproducible: oo
- Not Reproducilble: oo
- Issues:
  - There can be build differences for same versions (AFAIK)
  - I do get the feeling the environment.yml is supposed to tell me which libraries and library versions are needed /were used. but what does pip: /n git+ URL mean?
  - The date of the publications can give hints on the version used for the master branch (if the project is not an active project).

E:
- Reproducible: oooooooo
- Not Reproducilble:ooo
- Issues:
  - ...
:::






22. How about the dependencies (and their versions) of the packages listed on the environments above? Should they be listed as well?
    - What are you refering to exactly?
    - The environment file that just got shown has a bunch of other packages, not just python, seaborn and the two others. Should we have the full dependency listed. (I think this just got answered.):+1:

23. I didn't understand the issue with the master branch of git
    - In example we assume we are looking at/using a repository which is 3 years old. It is very likely that the master branch has moved ahead in these 3 years. Hence, the environment is dependent upon moving git branches and the environment is then not static or equal to what was 3 years ago.

24. could you go through an example with R? (not using conda)
    - I don't think we have time for that but I will highlight this to the instructors. 


## Recording environments
https://coderefinery.github.io/reproducible-research/environments/

25. Using containers = more HDD and / or RAM requirements on the hardware side ?
    - This really depend upon the size of the container you are running. A quick search on Docker shows that a minimum requirment is 512 MB, but Go or Java applications would require much more (4x, at least).

26. While docker /containers can partialy address the requirement of a snapshot of a machine,  Docker or containers or jails will not capture a machine because it does not capture the OS kernel. Docker only captures the userspace libraries when you specify the os version (ubuntu:20.4, etc). However, in the end you will be using the underlying OS kernel which might be different from the one used when building the container image. If you need a snapshot of the machine, then the closest you can get is by creating a VM image. 


27. What if we do not have the sudo? but for running apt-get we need that. right?
    - Docker can be configured to not need superuser. It is tricky, and might not work in all cases. [https://docs.docker.com/engine/security/rootless/]. Note the root user in the container is different from the root on the host machine. 
        - that crashes which what the instructors just said. ?! now I am confused.
        - Doesn't that just make a group of docker users, while the docker deamon still has root rights, i.e. you can still run stuff as root?
    
28. If you do not have access to the dockerfile that produced a container, how easy is it to probe a container and figure out either how it was created / what it does / potential for malicious activity?
    - Good question. I don't think there is an easy way to probe how the container was created. If you believe there is a potential for malicous activity, you should not use a undocumented container.
    - Docker does not keep a log of the activities / commands executed in the container, so you cannot accurately know how the image was created. 
    - There are tools to explore a docker container to see what's inside, but it can become difficult and not exactly possible to extract the dockerfile

## Where to go from here?
https://coderefinery.github.io/reproducible-research/where-to-go/
    
29. Is it common to have som document describing the overall project features: like milestone and/or dictonary of data. Somethieng like a central document?!
    - We will touch upon this when we discuss documentation(tomorrow). The short answer is that this something that can go into a Readme file in the git repository, or on static web page or on Read the docs. This is really dependent upon on how much effort you put into the documentation.

30. The Future-you point is really important - better to know that in advance rather than discover it from scratch, as it were. Future you is ignorant, and past-you was a jerk who didn't bother explaining anything :+1: 

31. For future you: just want to share this meme image that really hits home! [Meme](https://programmerhumor.io/wp-content/uploads/2022/10/programmerhumor-io-programming-memes-883f323e26a2eca-1011x1024.jpg)







## Social Coding and open software
https://coderefinery.github.io/social-coding/

## Social Coding
https://coderefinery.github.io/social-coding/social-coding/

32. Is the stream still here: https://player.twitch.tv/?channel=coderefinery&enableExtensions=true&muted=false&parent=twitch.tv&player=popout&quality=auto&volume=0.5 ?
    no one there yet?
    - It should be here: https://www.twitch.tv/coderefinery
        - thanks!

:::info
### Question 1: Why would I want to share my scripts/code/data?

**Choose many**. Vote by adding an `o` character:

- A: Easier to find and reproduce (scientific reproducibility)
  - votes: ooooooooooooooooooooo

- B: More trustworthy: others can verify correctness and find and report bugs
  - votes: ooooooooooooooooooooo

- C: Enables others to build on top of your code
     (derivative work, provided the license allows it)
  - votes: ooooooooooooooo

- D: Others can submit features/improvements
  - votes:oooooooooooooo

- E: Others can help fixing bugs
  - votes: oooooooooo0oo

- F: Many tools and apps are free for open source, so no financial cost for this
     (GitHub, GitLab, Appveyor, Read the Docs)
  - votes: oooooooooooo

- G: Good for your CV: you can show what you have built
  - votes: ooooooooooooooooo

- H: Discourages competitors. If others can't build on your work,
     they will make competing work
  - votes:

- I: When publicly shared, usually we time-stamp or set a version,
     so it is easier to refer to a specific version
  - votes:ooooooooooo

- J: You can reuse your own code later after change of job or affiliation
  - votes: ooooooooooooooo

- K: It encourages me to code properly from the start
  - votes: oooooooooooooooooo


### Question 2: The most concerning thing for me, If I share my software now

**Choose one**. Vote by adding an `o` character:

- A: It will be scooped (stolen) by someone else
  - votes:ooo

- B: It will expose my "ugly code"
  - votes:ooooooooooooooooooo

- C: Others may find bugs and mistakes. What if the algorithm is wrong?
  - votes: ooooo

- D: I will get too many questions, I do not have time for that
  - votes: oooo

- E: Losing control over the direction of the project
  - votes:ooo

- F: Low quality copies will appear
  - votes:o

- G: I won't be able to sell this later. Someone else will make money from it
  - votes: 

- H: It is too early, I am just prototyping, I will write version to distribute later
  - votes: ooooooooo

- I: Worried about licensing and legal matters, as they are very complicated
  - votes: ooooooooo


### Question 3: Why is software often treated differently from papers?

Free-form answers:
- Because the academia as a community is overly fixated on citations and pressure to publish. Software and data rarely yield as high-impact papers as "novel findings" -> data and code is not seen as something to invest resources in. Also less established career paths in data-focused positions (I know that data stewardship is becoming a thing). <- !!
- It is usually seen just as a tool, not a scientific product :+1::+1::+1::+1:
- Reproducibility of the analysis is often overlooked, sometimes people also try to obfuscate their results and analysis on purpose to make some perhaps erroneous conclusions?
- Lack of software expertise from reviewers.
- Not peer-reviewed
    - See [JOSS](https://joss.theoj.org/), [rOpenSci](https://ropensci.org/) and [PyOpenSci](https://www.pyopensci.org/)

- No built-in incentives to provide high quality software in the same way that papers come with incentives

- ...


### Question 4: When you find a repository with code/library you would like to reuse, what are the things you look at to decide whether you use it?

Free-form answers:
- What is the licence and what it allows
- Who wrote this, maybe what affiliation the authors have, is there credible work that they also do, or maybe what kinds of publication they already have, etc.
- License, language (python/R/etc) :+1: :+1: :+1: :+1::+1::+1:👍:+1:
- how did I find it (who used it for what purpose already; recommendations)
- Would it be easier to adapt this code, or to write it from scratch?:+1:
- Easy to adapt to my project/code :+1: :+1:
- How recent the activity on the project is
- Whether there are a lot of unmerged pull requests waiting for feedback, indicator of maintainer health
- If it use testing

:::

## Software licensing
https://coderefinery.github.io/social-coding/software-licensing/

32. What is the difference between conda and docker? (I ask specifically b/c of environments)
    - Conda is a way to install software packages (Ptyhno/R/C etc), and make a self-contained directory you can activate and use that software.  It still basically runs on your computer.
    - Docker is a tool that makes "containers", which can have sofware installed, but it's like it contains the whole operating system.  So it's more strict, a bit more complex to make, and more portable.

33. Why would I use docker v. kubernetes? Can you explain a bit more what bootstap is?
    - Docker is one program to make and run containers. There are others like it.  Whatever you use, it is good for running single things.  It can be practical for running one-off software things.
    - Kubernetes is a whole system that manages running many containers and services.  It's mainly used for things like running web servers and other persintent services (but could be used for much more).

34. When you license your code, does it belong to your employer or you? how does this work with patents v. licenses? :+1: 
    - It depends on your job contract and your employers policy.
    - --> follow up: so if the data belongs to the employer, does the code also belong to the employer? What happens when you change jobs and you want to showcase your work then?
        - If it is just for showcasing your work you are probably fine, but if it is for using your code your are dependent upon your agreement with your employer. Though the data belongs to the employter, this do not necessarily reflect upon the code. You could still be able to take the code along with you, but it depends the agreements governing your work.
    - --> what type of license would you need for this use-case?
        - MIT License gives you a lot of freedom to do what ever you want with code you write.

35. Where should you put instructions for using the code -- in the README.md file?
    - Yes, usually setup/install and how to use are part of the README of your project. It is a very important part too.


36. Following up on ChatGPT, how do you cite it if you used it as part of your code for ideas?
    - You would become the owner of the code. However mentioning that you use GenAI to create the code depends on the usecases. Personally I don't mention it unless I'm publishing for journal.
    - --> how do you state this, on GitHub after you publish? in the README or elsewhere? Is there an EU Commission or somewhere else that we can follow for guidaince on this?
        - I noticed some repositories which mention this in their README. However this is still a new concept and there is no muture/standard way yet.
    - --> is GitHub Copilot considered 'better' than OpenAI for code?
        - Not sure if it is better or not... Perosonally I use OpenAI and Claude.


:::info
### Question 5: Which of these are derivative works?

**Choose many**. Vote by adding an `o` character:

- A. Download some code from a website and add on to it
  - votes: oooooooooooooooooooo

- B. Download some code and use one of the functions in your code
  - votes: ooooooooooo

- C. Changing code you got from somewhere
  - votes: ooooooooooooooooooooo

- D. Extending code you got from somewhere
  - votes: oooooooooooooooooooooooo

- E. Completely rewriting code you got from somewhere
  - votes: oooooo

- F. Rewriting code to a different programming language
  - votes: ooooooooo

- G. Linking to libraries (static or dynamic), plug-ins, and drivers
  - votes: oooooo

- H. Clean room design (somebody explains you the code but you have never seen it)
  - votes: oo

- I. You read a paper, understand algorithm, write own code
  - votes: ooooooo
:::

37. I like the CC licenses because the content in the licenses is easy enough for the average user to roughly understand. However, I haven't seen any mention of warranty or liability in the CC license, unlike in the GPL3 licenses. Can I be held liable for something if I have a bug in my CC-licensed code?
    - No you are not responsible for any possible bug/mistakes.
    - If you are talking about software, CC licenses aren't recommended to be used for software: https://creativecommons.org/faq/#can-i-apply-a-creative-commons-license-to-software .  There are only a few major software licenes you need to know that are roughly the equivalent of each of the CC levels.
        - Thanks!

38. I did ask Chat GPT for an algorithm and it found something, which i used. However, i am sure that the algorithm exists somewhere else. Do you've got a hint on how to find the original publisher? Chat GPT just gives reference to some general algorithm books.
    - You can try to search part of the algorithm, or the algorithm name.
    - For clarification: An algorithm itself can't be copyrighted.  The code of that algorithm could be.
    - Thank you both!

39. What about AFL (Academic Free License)? Allowed to use, but no changes are allowed. Reduces the workflow for the original author...
    - "others can't modify" sounsd good but is a trap: would someone want to resuse and improve it, if it is "dead" and your improvements can't be re-shared?  Most people wouldn't recommend this :+1:
    - "can't modify" isn't considered "free software" and most projects will stay far away from it
    - Note that an author never has any responsibility for doing anything.  If you are tho only one that can modify, wouldn't that make more effort for you since you have to fix it?  If others can fix and re-share, then you don't have to feel bad about not doing anything else.

40. How does naming the tool work, both pre- and post- publication? Is there licensing for the name and/or copyright?
    - "trademark" is the thing that covers protection of a name or identity.  Copyright isn't relevant for a name.
    --> how do you establish a trademark, pre- and post- publication?  See 44 below

41. Does the tool belong to the University, or to you as the developer? Or is it shared across both?
    - As an instructor said "it depends": usually your employer would own it but at least in Finland it can be more complex depending on funding source.  Always check up the rules at your own place.

42. Should you wait to post anything to a public GitHub until the tool is published?
    - What do you mean with tool getting published?
    - It really depends on your interests: "I release when my publication is ready" or "when it's done" are valid, but also "I'm being radically open to get more interest".
    - But things are rarely "done" so release can get delayed more and more... and if you don't plan for release from the start there might be private and public stuff mixed together and it gets harder and harder.

43. Yeah licenses considered "open" can't be closeable retrocatively (old versions, new versions can be changed - if they still hold the full license).  It's one of the standard tests for free software licenses.
    - The author of the code can release the code under several licenses. So, I can release version 1 as GPL, and version 2 as (C)
    -  Yes.  This kind of GPL for the open version, and closed license sold otherwise, that is often done.  But you can just release under the GPL and if anyone wants more than the GPL offers, they contact you and negotiate another license.

44. How do you establish a trademark, pre- and post- publication?
    - Check with lawyers unfortunately.  It's a thing you need to register.  (Most academic software doesn't do this.  Unless it's truly big or commercialized, it's not really relevant)
    - --> where do you go to register?
    - A quick search finds this: https://www.euipo.europa.eu/en/trade-marks - I haven't use this, I don't know if it's relevant, maybe it's per-country?

45. . Can I add EUPL license to GitHub? I cannot find the optione there
    - I haven't checked but I believe you, they have relatively few automatically pickable.  You can always copy the text and put it in the LICENSE file yourself


:::info
**Break until xx:02**
:::


46. Here are the three "free software" tests used in the Debian linux distribution.  I think it has some good lessons
    - "desert island test": can you use and modify it and share with others on your island if you can't communicate with anyone?  "send improvements to me" or "send me an email if you share it" don't work.  This would also mean you can't cite it, for example.
    - "dissident test": if you are hiding/don't want to communicate and share your actions, can you still use it and share with your friends?  This is useful even in academia because do you want to *have* to publish just to meet some criteria?
    - "tenticales of evil test": if a big corporation bought it from the author, can they retroactively stop usage, make you liable for something, etc.  This is very useful for us anyway, we wouldn't want to use something with an unclear future.

47. what if I want to publish some code that is "just" to do some data exploration, analysis and plotting (as addendum to a paper, for example). Is that by definition also "software"? How would you licence?
    - We can debate what the definition of "software" is, but in practice everything we are talking about equally applies to this case.
    - I'd throw it somewhere, give it a basic readme and license, and not worry too much.
        - what is a basic license?
        - "basic" in that sentence doesn't mean too much but what i would do: MIT if it's "small, anyone can use for any purpose" or GPL if "this is somewhat valuble to me and gives me advantage, I don't want others making closed versions that I can't access."  These are basically my go-tos that don't require any thought but gets the main two levels.  (roughly like CC-BY and CC-BY-SA, for the comment about CC licenses above)
            - thank you! very helpful


## Software citation
https://coderefinery.github.io/social-coding/software-citation/

## Sharing data
https://coderefinery.github.io/social-coding/sharing-data/

48.  I have a question regarding github/-lab etc. accounts. When I get employed in a new job and my new employer pays for a professional type of account - how do I add or connect this to my existing account? And how do I disconnect again after the contract ends?
        - Some companies don't accept using personal repositories to be used. Of course it depends on the companies policy and the fact on what project you are working on. In the end, for the companies who accept using a peronal account, they can add you to an organization during your employment and then remove you after your contract ends.
            - so maybe I have to get a new account when I start for a certain employer in order to get the "professional" flavour they pay for? How do I link this (and possibly multiple such accounts) with my private account that hopefully stays?
                - My experience was they pay for the account and manage the account too. For example all the accounts are created using the companies email address to make sure after your contract ends, you don't have access to the repositories anymore.
                - In the end, private and confidential work are undernstable. If you work on something confidential/private with your company account, you can explain it to the next employer; even if you don't have the code publicly available.
                - Counter question: Why do you want to link he two? If it's about showing the work you have done, you can indicte the other account, but otherwise?
                    - I was mainly thinking about how I could benefit from the fact that the company pays for a professional account that has more options. I realized I don't see / cannot use many of the options in my privat github that we worked with in the workshop last week

49. If you publish a methods paper where you develop a code, you make the code available and citable, and you then write the "software-paper", wouldn't it divide your citations?
    - Possibly. But it also depends on how central your methodology/code is to your research paper. Your research paper might e.g. not get any traction from the computatioal side, since they are not interested in your specific topic. But if the algorithm/code is more general than your field, you could get citations from places you would otherwise not have been seen. 


## Feedback

:::info
News for day 4 and prep for day 5:
- We covered the topics in the schedule.  Any exercises are homework for you (you can ask for help via our chat, or from your colleagues)
- Tomorrow is
    - Documentation (which follows up from today somewhat - make your own webpages via Github)
    - Juptyer Notebooks (which many people probably know, but we go more: version control with notebooks, sharing, and so on.)
    - Again, demos only and exercises can be done afterwards.
- .
:::

Today was:
- too fast: oooo
- too slow: 
- right speed: ooooooooooo
- too advanced:
- too basic: o
- right level: oooooooo
- needed more exercise time: o
- needed less exercise time: 
- I will use what I learned today: ooooooooooooo
- I would recommend today to others: oooooooooooo
- I would not recommend today to others: 
- too slow sometimes, too fast other times: ooo

One good thing about today:
- Snakemake 🐍 :+1::+1::+1: :+1:
- Many resources for reproduciblity to explore. :+1: :+1:
- I liked that many topics were introduced in a basic manner, thus giving us the tools to expand upon them further on our own time, based on our needs. :+1:
- Learned what copyleft actually means
- Shared experiences, thank you very much!
- ..

One thing to improve for next time:
- I would love more time in the demos and excercices. :+1:
- Never quite understood snakemake, could maybe use a bit more time on this :+1:
- Cats? :( 
    - Unfortunately has been at the vet...
-




Any other feedback?
- Never thought copyright and legal issues could be interesting :D :+1:
- could you comment on how to get the 1 CP certificate? which homework to do?
    - I think this page would say everything: https://coderefinery.github.io/2024-09-10-workshop/certificates
        - thanks!
        - follow up: "During the workshop we will provide with contact addresses where you should send these documents to." which is that?
    - Is it also possible to get a certification if you attend only day 4, 5 and 6? 
- A lot of important information that is difficult to get into yourself, this really helped getting started!
    
    
For those in groups, how many people are you watching with:
- .
- .
- .



