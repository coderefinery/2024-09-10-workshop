+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 2"
+++

# Day 2 - 11/09/2024

## Icebreakers

Let's test the notes with some icebreakers! :icecream: 

- What was the last animal you saw?
    - neighbor cat
    - two cocker spaniels 
    - neighbor shih tzu dog
    - Western jackdaw
    - CATS :+1:
    - borderterrier x3
    - cat
    - dog :::+1::+1:
    - hare
    - sparrow
    - homo sapiens :+1: 
        - technically correct, best kind of correct
    - hedgehogs <3
    - A tricolor cat :) 
    - small forest hare
    - A dog on its morning walk
    - My dog
    - My cats and my husband
    - neighbor cat walking past
    - A frog
    - A dog, viking one, vestgøtaspets / vallhund
    - A squirrel


- Which path did you use yesterday to interact with Git?
   - GitHub: ooooooooooooooooooooooooooooooo
   - VS Code: ooooo
   - Command line: ooooooo
   - I wasn't here yesterday (no problem): o 
   - I wish you offered a path for a different tool:
      - GitLab: oooo
      - RStudio: oooooooooo
      - JupyterLab: oo
      - Spyder: oo
      - Pulsar: o
      - Pycharm
      - (please add your tool) 
   - Does anyone else use a combination of the three?
       - I tried at the beginning, but was getting too tedious to track everything…
       - I'm used to GitHub Desktop / VS Code combo
       - I'm generally working in spyder/command line
       - I would like to use VScode /command line / Rstudio / overleaf
       - I started with Github and then a combo of VScode / command line 
       - I tried Github & command line, but it was confusing with a command line
       - I used Github, tried a few Git commands, and tried Git on RStudio locally (but it is a bit broken, maybe issue between chair and keyboard)
       - I tried mainly the command line, and supplemented it with GitHub
       - I used command line, Pycharm, GitHub Desktop


## Introduction, day 2

We will start today at https://coderefinery.github.io/git-intro/

1. Is this the place to ask?
   - yes!  Anytime, we are always watching
   
> My question is your question, which is their question, and our question, and so why do we not mind our business of asking questions ?

2. I wasn´t able to create a tag in a branch: There was an error creating your Release: tag name can't be blank, tag name is not well-formed, published releases must have a valid tag. The name was v1.0.0, so I didn´t understand
    - Yeah, that's weird.  Do you have someone to look at together?  Or maybe the "bring-your-own-code" sessions later?
    - But don't worry: this doesn't affect anything else in the workshop.  (and isn't used that often anyway)
    - I had the same problem, realised there is a drop down menu near the top to set the version, the name is separate:![](https://notes.coderefinery.org/uploads/ea72b3d7-eb55-4566-9a6d-95e7559a066b.png) => Done. Thanks!

3. Not sure yet how to use git in the command line as opposed to a graphical interface
    - It's OK!  We haven't taught it yet, hopefully you will see some today.
    - (we offer those other options for people who knew GitHub web and wanted to try more, or reviewing again later)

4. Do I need to setup VS Code in any way?
    - It is pretty automatic in most things, including the Github link.
    - There were a few things here: https://coderefinery.github.io/installation/vscode/ (only important one is setting VS Code as the editor for git, but that isn't needed)

5. It would be helpful to know how to 'clone' a repository which exists only on a local git, and work with it in the same way as if it were on Github, if possible. Thank you!
    - Do you mean: you have it local, and you would like to make a copy to GitHub?  (If so, we'll get there: that is more abstract so we rephrased the lesson to the current order.)
    - No, not quite. I do not wish to copy it to Github. It is a local repository on a local git and I want the 'main' to remain local for the time being. May be the term would not be 'clone', I cannot say, but it is on the same computer.
    - Ah, you mean: clone directly between two computers you control?  Or on the same computer?
        - Yes, this can be done.  `git clone` can work with a local file path.  Or `ssh-computer:/path/to/repo.git` and clone that way.  Also check out "bare repositories" which are made for local main copies that are cloned other places.


## Local workflow
We are here: https://coderefinery.github.io/git-intro/local-workflow/

6. It would be nice also showing command line, not only VS code
    - Yes, we agree.  Unfortunately we have limited time, but throughout the workshop you'll see more and more (so that if you read the material again, command line options probably make more sense!)  That's our goal at least. :+1:
    
7. As for best practices, could you give some tips as to in which occasions is best to clone locally as opposed to keep it 'online'?
    - Anytime you want to work on a project locally you need to clone. For small changes it's a matter of taste. 
    - Really in most real cases, you will make a local copy, since local editors and testing is much more useful.  The web was good for showing new things in a way everyone could do.

8. B's mic is low volume compared to R's
    - Thank you for notifying! We try to fix.
    - no, not R's I think.   R was fine. It's B's one
        - Fixed now, it's B's mic that is low

> Thank you for clarifying the difference between a clone and a fork and its respective consequences. It would be nice if exactly this comparison and their consequences/intensions could be part of Coderefinery's git intro's document. Both are explained but not compared so it might be confusing for beginners.
    > Good idea! :+1: :smile: -> https://github.com/coderefinery/git-intro/issues/471 (you can also add issues and comments to the lessons yourself, we will be working on them before next workshop) :+1: awesome, thank you for the tip!


9. Is it possible to merge clone back with original repository (pull request)?
    - Yes.  You can "push" directly (we'll see later) if you have write-access, or make a pull request (anyone can do this to a public repository).  Good question, this is one of the main points of today!


### Exercise break: Local workflow (we resume at xx:53)
https://coderefinery.github.io/git-intro/local-workflow/#exercise

- This is a local exercise, there isn't a GitHub web track (there is another one of these later)
- You'll practice making a local copy (clone) of something that already exists, and doing many of the same things as yesterday (but slightly more advanced).

I am:
- done: oooooooooooo
- not trying:
- had major problems: ooo
- wish for more time:oo


10. When should one use ssh and when should one use HTTPS when cloning a repository? 
    - you need ssh if it is a private repo
    - https is fine if you want to clone but are not planning to push changes
    - if you plan to push changes back, you need to authenticate and on linux or mac this means using ssh
        - Will this create a problem if I use https when using VSCode if I want to push to the repository that has been cloned.
           - I think with VS Code it will work anyway since VS Code uses a different authentication mechanism. You can try to push changes back to your fork.

11. I've had this issue yesterday too, I want to create a new file in the branch I created with command line and not VS code (which I have tried and works fine) with the following `git add new-file.md` but I keep getting this error : `fatal: pathspec 'new-file.md' did not match any files` I though `add` would allow to create the file but it seems it need to be there already?
    - That's correct.  `git add` begins tracking existing files, not make new ones.
    - Okay thanks, maybe it would be good to add the code to create it in command line then (in the instruction I mean).

12. I cannot clone with SSH from the cr-workshop-exercises with my user. Do I then need to first fork to my github user to have that access for cloning? Oops, nevermind, I just had an extra letter in the command..!
    - :+1:
    - good - it should be possible to clone either

13. I am trying VS Code, there is no option  “Clone Git Repository…” under Start in Welcome tab.
    - `CTRL + SHIFT + P`  might also give you a menu where you can search for `git:clone` 
    - Thank you (/me writes down shorcut). That also failed, removing Github codespaces extension fixed.
        - :+1:

14. When you modify locally a file that already existed, do you need to do git add before commit, or commit is enought include these  changes?
    - Check what happens if you try it out :) 
    - I see hahaha. Thank you!
    - For anyone else reading: yes, you need it.  Unless you `git commit -a` (add every change automatically) or `git commit -p` (show me every change and I choose yes/no)

15. "The default branch name in Git has been master for a long time, but it is changing to main in many places. We recommend to set it to main for new repositories that you create locally" --> what does this mean?
    - 'master' used to be the default everywhere for the inital branch when a repository was created, both if you created the repository locally, or if you used something like Github. Github has stopped using 'master' and instead uses 'main' - the git installation you have for working with git locally, still uses 'master'. This will cause problems when keeping the local and remote repositories synced with each other.
    - oh okay! when did they change this?
    - A few years ago I think? Not 100% sure - something to do with the negative connotations with slavery and masters
    - wow, thanks for the explanation, so if I don't change this locally, it could cause some issues?
      - it's not really a problem if you created it locally with a different name. it is no problem to rename branches later. the rename can happen locally but even easier it is to rename branches on GitHub or GitLab. 
    - No worries :) Yes, as far as I know (I'm not an instructor btw) branches on the local and remote repositories should be named the same
    - In general no issues if you don't change it.  These days you have to look at every repo and figure out what the default branch is anyway.

16. A useful setting for the p aliases: git config --global interactive.singlekey true --> what does this mean?
    - You can push "y" instead of "y ENTER". (or 'n' insteaf of 'n ENTER').

17. Which is the difference between 'git switch' and 'git checkout' (what I usually use)?
    - `git checkout` has existed since git started, but it has two very different meanings (change branch, or restore files to old versions).  `git switch` and `git restore` were added a few years ago to make it more clear for people learning.
    - You can use either, my muscle memory is also still "git checkout".

18. I apparently have forgotten the password to my public key so I do not have permission to clone.. how can I reset this?
    - One solution would be to make a new key pair and add follow the setup instructions again. Maybe someone else also knows another solution?
    - Can you explain how to do this, like send link to the play by play instructions?
        - We have the instructions here: https://coderefinery.github.io/installation/ssh/
        - Thank you, will check!

19. When I check git branch --all, I get a remotes/origin/HEAD -> origin/main -- what is this compared to the origin/main ? 
    - Oh, you found something good!  So yeah, `remote/origin` shows a view of branches on GitHub (or wherever you cloned from).  You'll notice these update when you push to GitHub.
    - The arrow says "these branches are related", what is the upstream of another.  If you `git push` it knows that `main` on `origin` is where to push to by default (and pull from).  Usually it's automatically set up.

20. I did not understand how to do this exercise... I'm on GitHub and I found the place where I could clone my recipe repository (the forked one) and I have downloaded the folder. My question is: How can I open the downloaded file to make the changes?? I try to copy the HTTP link and open it on GitHub, but the changes were updated also on the original file.
    - we will show on stream
    - I'm not sure I fully understand the question, but the HTTPS link, you would paste into the `git clone` or VSCode clone command only.  In this example you don't download directly.

21. can you explain what this "tracking" does (8)?
    - Basically it means "default push and pull location".
    - When you push, you don't have to specify a branch name.  And `git pull` or `git fetch` with no arguments knows what to do.  You don't have to know details yet though!

22. Im working in VS Code. After merging the branch into my local main repository, should I delete the branch? How should I do it? Through git hub it seemed much more intuitive. 
    - You can delete it, but it's not needed (many people leave branches around since there's no real problem, except clutter)
    - (can someone fill in how to delete a branch in vscode/)
    - Seems you can under the source control view

23. This was a nice exercise. But I am unfamiliar with some of the common commands of git. Anywhere you guys suggest to have a summary of the most common commands for git? Pretty intuitive, but I just don't know them.
    - Check out this awesome cheatsheet "git the way you need it" by Aalto Scientific Computing: https://aaltoscicomp.github.io/cheatsheets/git-the-way-you-need-it-cheatsheet.pdf
    - if you just need the commands, without detailed explanation, this one is nice (highly recommend to also check out other comics and zines): https://wizardzines.com/comics/every-git-command/

24. I dont think I understand the output of "git graph". Can you explain it what do I see with all the /|\* sign?
    - It shows the same as the "Network view" that we saw on Github before, but an ASCII art version.  Newest commits are at the top.  You can see where branches split and merge via the /\| characters.

25. I created a branch (of a forked repository), and made changes to the branch, commited and pushed the changes to the branch, then merged the branch and deleted it locally. However, I can still see the deleted branch on github? Is this expected? What must I do to ensure that the deleted branch (locally) is seen on github
    - Yes, it's expected.  There are two different remotes, and it needs to be deleted on both sides separately.  (you can delete the Github one locally, for example: `git push origin --delete BRANCH_NAME` I think) :+1:

26. Sometimes, when I type:
        git status
        On branch main
        No commits yet
        nothing to commit (create/copy files and use "git add" to track)
        --> For some reason, when I next type git branch, it doesn't return anything: why does this happen sometimes? (it's not consistent, it should be showing *main)
    - If you have not made any commits, git branch does not show anything yet (at least on my machine). The point is that a branch is a pointer to a commit (spoiler alert), so if there are no commits yet you are in a strange state, I guess?
    - Oh.  It could be that somehow the display is messed up: this used to happen to us sometimes.  How are you running Git?  (operating system/platform?)
      - ~~command line, ubuntu~~ (wrong person)
      - Hm, then I'm not sure
    - Running it locally in the terminal on my MacBook (I first did git init, and then changed the git config file to include the branch would be main, not master, then did git branch after git status)
        - Hm, I don't know of any problems that could happen here either.
    - I wouldn't worry about this now (focus on the lesson), but does `git --no-pager branch` show anything?
        - nope, just tested, this has been an ongoing issue that it is not consistent on my MacBook and i don't know why it works sometimes and not others
        - (unrelated: I was always using `git ... | cat` to get rid of the pager! I did not know there was a `--no-pager` option! This made my day)
        - what does the pager do?
          - it makes so that the output of the git command is not printed directly on a terminal, but opens a "pager", like when you look at man pages. In other words, it opens a separate program inside your terminal that you can close afterwards and puts the output there, and when you close it (typically with q) the output is gone and you don't see it in the terminal any more (sorry for the verbosity). 

27. Can't see the entire width of code window / terminal :+1:
    - thanks for pointing this out quickly.
        - What was the content of the git checkout command he wrote?
            - "git checkout -b new-branch": create a new branch called new-branch and switch to it.
            - longer version:
               - "git branch new-branch" (creates branch)
               - "git switch new-branch" (switches to it)
               - "git switch -c new-branch" (creates & switches, like checkout -b, but easier to remember)

28. You do write a summary of the answer in the notes if you answer verbally, right?
    - We will, it might not happen right away, but latest before archiving the notes we will fill all gaps. Anything specific you are missing right now?
    - No, thank you, I was just wondering, since we are working on several windows and following the stream etc. so I don't want to miss anything. I also want to go through everything later one more time, to repeat everything.
        - Ok, you can watch recordings and see the archive linked from the event page :+1:
                - Notes archive: https://coderefinery.github.io/2024-09-10-workshop/questions/  :+1:
        - do point out if we forget to write somethinge, also if we have forgotten to answer something in previous days.  :+1:
        - This notes document is excellent, thank you. Great idea! :heart: - It really is, because normally you get to ask in a chat and get answers only verbally, sometimes in the chat, so it gets super confusing. In this notes document, everything gets asked, answered and edited in real time - while keeping everything in order.
  
29. Why stage and commit in 2 steps (instead of a single step)?
    - You can commit in one stage if you want.  We have two stages to clarify what is happening (and it's useful sometimes, when you want extra verification before committing).
    - we will also discuss this later during https://coderefinery.github.io/git-intro/level/#how-about-staging-and-committing

30. git switch command doesnt work for me: "git 'switch' is not a git command. See 'git --help'." Is my my git version too old (2.11)? which version should I use?
    - this is maybe older version of Git. In this case:
      - "git checkout somebranch" switches to branched called "somebranch"


### Break, we resume at xx:15


31. What would be the main advantage of using the command line over VS Code? I find the command line less intuitive and more difficult to navigate. Especially not knowing the commands. I’m trying to figure out if it's worth investing significant effort into getting comfortable with it, or if it doesn't make much of a difference when starting out.
    - You are right that most thinsg can be done in VSCode and other editors: and yes, that is much more convenient these days!  For some people command line can be faster, and it allows one to do some extra advanced things.  Don't feel bad about sticking to VSCode for now.
    - For commands, no need to remember them all: Check out the cheatsheet: "git the way you need it" by Aalto Scientific Computing: https://aaltoscicomp.github.io/cheatsheets/git-the-way-you-need-it-cheatsheet.pdf :+1: Awesome cheatsheet, thank you for making the effort!
    - The command line in general is important also for reproducibility. (You have a written history (checkout `history` command in command line) of what you did vs remembering where you clicked)
    - I'm using linux, on that command line is a general integrated tool
    - I was recommended to use this introduction to the command line: https://swcarpentry.github.io/shell-novice/ and I have to say that it is a very good and intuitive way of learning the commands. Very good explanations and easy to follow the exercises. 
        - :+1: Software Carpentry has very good courses/materials for the basics of command line and more: https://software-carpentry.org/lessons/ :+1:


## Inspecting history

https://coderefinery.github.io/git-intro/archaeology/


32. How do I find the commit overview on the Github Page? The upper part of the stream is blocked by the speaker camera..
    - From the code page, clock icon above the file list (is this it?)
    - Should be the clock-resembling icon under the big green button

33. In the upper left corner of some of the commits, there are red and green squares. What is the meaning of these squares?
    - I believe that it is just another way of visually representing what happened in the commit (lines added (green squares), lines deleted). Anyone has more insights?

34. Can you write the reduced version of the hash when using the CLI option as well (git show 347e62 for example)?
    - yes!  Shortest unique prefix (7 characters is "always" enough)

35. Is it possible to compare line by line what got changed compared to the original?
    - In some commit views yo ushould see this: green background line=added, red background=removed.  Is this it?
    - Thanks. yes.

36. How can you find/know the hash of a commit?
    - command line? if yes, then "git log" or "git log --oneline" shows an overview of commits and there you can see the hashes (which are unique identifiers) - I meant command line and I found it thanks!
    - or did you mean on GitHub?


### Exercise break: Inspecting history (we resume at xx:53)
https://coderefinery.github.io/git-intro/archaeology/#exercise

- Try to do what you can: the next parts don't depend on this
- Most of the answers and hints are on the page.
- **Update:** if you haven't done a `git clone` locally before (command line or VSCode) in the exercises, it might be hard to do it locally now.  We recommend trying this on Github instead now (it's not perfect but works).

I am:
- done: ooooooooooo
- not trying:
- had major problems: 
- wish we had more time: ooo


37. I am trying to step out of a repository using CLI, but I am not getting"fatal: not a git repository (or any of the parent directories): .git
    - what command are you using to "step out"?
       - are you on the command line?
       - I am using `cd ..` and chekcing with `git status`
           - For git status you need to be within a directory that has the .git file, what would you like to check with `git status` in this case?
           - you can check the directory you are in with the `pwd` command. If you have a `.git` in the directory you are in, but that should not be a git repository, then you might need to delete the `.git` (but ask for directions, this can be tricky and risky)
            - ok, it seems there is one in my user folder for some reason.... is there a guide i can follow to safely remove it?
            - What operating system are you on?
            - `rm -rf .git` would remove it, if you are in your user directory.  You can also delete it from the file browser. but `rm` is a dangerous command if done wrong, so be careful.  Removing .git shouldn't ever remove real files, though.  If you can get someone local to watch over your shoulder when doing this, it'll be less stressful.
            - I am running MacOS Sonoma.  - ok, then command above should work
            - Ok, i removed it and my mac is still running, so I assume I am fine for now.  Great!
              - for next time: further down is a bit safer approach: rename it to something else (this will make it invisible to git), move it to somewhere else. and after a while you can remove it. 
            
- " when using git status. What am I doing wrong?"
    - what do you see instead when you type "git status"? are you inside another repository? and the exercise should still work if you clone a new repo inside another repo. it's not "pretty" but it will work.
    - This is what I see: ![](https://notes.coderefinery.org/uploads/55adf8bc-d179-40e9-8768-f9f668f4c56a.png)
    - And the list just goes on further down...
       - probably a git repo was created "git init" too far on top of your file tree and now "everything" is a git repo. no problem for this exercise. everything in a git repo is in a directory called ".git" so I would look for that one on your hard drive and rename it (until you are sure you can remove it).

38. How can I open and modify a clone file that I have downloaded from GitHub if I don't know how to use the command line, nor VS code, nor RStudio? I don't know what is an editor, can you make some example? The only things I know is that I use Spyder when I have to make a script in python
    - which editor do you use normally to edit text files on your computer? (and it's no problem to say none).
    - like when you write code or a script, using which editor do you write the Python or R or Matlab script?
    - but in doubt I would try with VS Code where you can navigate to the directory created by cloning the repository.
    - Did you download it by `git clone`?  If so, it becomes a directory on your computer and you can open it in Spyder.

39. git grep "text" tells me the location of the file where the string is connected. Is there a way to get extended data on that file to know which commit added the string that I was looking for?
    - unsure but once I know the file, I do the second thing in a separate step: "git annotate filename". but it is possible to combine (chain) commands in terminal shells like Bash.
    - You can use `git log -S "text"` and you will get the commit that created that, without using `git blame` or `git annotate`. Adding the `-p` option will likely also give you some context. But the exercise here is about `git annotate`, and then searching in its output with `/text-to-search`

40. I am resetting up my key on GitHub, and I've reset the password and the config file. How do I get the public key ID to paste into the GitHub remote (online) version in the browser from there? Like what commands do I need to obtain this?
    - The file is in `.ssh` in your home directory, whatever that is on yoru computer.  This command might print it to your screen: `ls ~/.ssh/` and something like `cat ~/.ssh/id_rsa.pub` or `cat ~/.ssh/id_ed25519.pub`
    - So I have both id_ed25519.pub and id_ed25519 --> I assume the one without the .pub extension is private? So i should always use the key that ends with the .pub when connecting to GitHub or GitLab? in what cases do I need my private key then?
      - your private key is used by SSH. You do not need to do anything with it directly. The public key you can copy and give around to any site you want: by using the information in the public key, it can verify that you own the private key. 
      - Got it, so is it distinguished by the .pub at the end?
        - yes

41. Follow up of question 38: Are you suggesting to download the file from GitHUb and then (when the file is on my computer) open VS code to modify the script? And then I can test that the modify I apply are not updated in GitHub, right? (like you ask us to do in the exercice)- I click the button "Code" in GitHunb and then it suggest different options. One of them is to download the file as zip file.
    - How did you download the file?  Did you `git clone` it or download one file?

42. If you're cloning a repo on the GitHub browser, you click code --> clone but do I need the command line at all or can I somehow clone it just into my local repo some other way?
    - if you clone from command line, you need "git clone WEB-ADDRESS" but if you use tools like VSCode, then I only need to paste WEB-ADDRESS into the form where VSCode asks me where I want to clone from.

43. Is it a good practice to fork the repo and then clone locally if I want to make contributions to existing repo on github ?
    - Forking is needed to make sure the original repository and your repository can communicate easily (e.g. making PRs). In order to modify the content efficiently, you typically need to have a copy on your machine, and that is what you get with cloning (cloning YOUR repository and not the original one might be easier). 

44. I am in the terminal in VScode and do git annotate. It prints out the annotation in the terminal. How can I search it? typing /logic error throws an error "bash: /Logic: No such file or directory"
    - it looks like the output of git annotate did not end in a pager, which is the thing you can search things in using `/`. Is there a way to search for text in the pane where the terminal is? 
        - no I can not find a way to search the terminal
          - perhaps you can try ~~`git annotate | grep <what-youre-searching-for>`~~, composing `git annotate` and `grep` with a pipe (`|`)
              - this gives me a git help window: git annotate | grep "Logic error" networkx/algorithms/threshold.py
                - sorry! it should be
                  ```
                  git annotate <file-name> | grep <what-youre-searching-for>
                  ```
                  with the other command git is complaining that you are not giving it the file name to "annotate". My bad.
                  - great thank you! this works:  `git annotate networkx/algorithms/threshold.py | grep "Logic error"`
                    - well done adding double quotes `" "`
  
45. Using the git annotate on the file in the exercise, to try to find the latest commit, it is not in chronological order. What is the sorting of the printout of git annotate FILENAME? And maybe there is a way to get it to show latest at the top?
    - The ordering of the lines is the one you would have when you open the file normally.
      - If you really want to reorder the lines in chronological order, from the command line you could use 
        ```
        git annotate FILENAME | sort -k 4 -r  # 4 here is the 4th column, the one that contains the date, -r means `reverse`.
        ```
        using the sort command. But this would reorder the lines to a point you can't recognize the file structure any more.

46. I have to leave and cannot participate this afternoon unfortunately. What will be the key learning outcomes? Thanks so far, great course!
    - No worries, you can also watch the recording later. You can find the objectives of the afternoon session at https://coderefinery.github.io/git-intro/sharing/ . We will send a summary e-mail including preparations for tomorrow later today.



## Lunch break, we resume at xx:00

- Next session will start with a recap of the morning
- You can continue asking questions below
- But also remember to take a break, questions will be archived and available for you also after the workshop to read :)


47. I am now in the last step of the exercise, where I want to create a branch at the commit before the one we have identified, but I get "invalid reference" with the code below. Maybe I should write the HASH number explicitly, not as a subtraction.
    ```
    git switch --create just-before-commit-changing-print-logic-error 90544b4fa5-1
    ```
    - what is the command that you have typed?
        - Added now. Should the last variable be typed as 90544b4fa4 instead of 90544b4fa5-1? 
          - Wait: that is not a `-` (minus) you need there, it's a ~. 
            `<commit-hash>~1` means "the commit just before `<commit-hash>`".
            And notice that commits are random-looking values (hashes), that depend on the content of the repository content at the time of the snapshot (among other things). There is no easy relationship between a the hash of a commit and the hash of its parent. 
        - Got it, thanks! It is correct in the course material (~), I just have it zoomed out too much..

48. For the last step, I don't have the new version of git. What can I use instead of git switch?
    - you can use `git checkout`
        - I mean for the whole command: git switch --create just-before 90544b4fa~1
          - you might have to try 2 commands
            ```   
            git checkout <commit-hash>~1 # to get to the desired commit
            git checkout -b just-before # to create a branch starting at the   commit specified at the command before 
            ```
            but actually `git checkout -b just-before <commit-hash>~1` should also work.
            Replace `<commit-hash>` with the right value.
            
49. It takes pretty long time to run ("Updating files: xx%...)". Is it just me or is it normal?
    - the whole repository takes ~100 MB. Depending on your connection this might take a while.

50. What are these (when doing git graph)?
    --> origin/main, origin/HEAD, name-of-subsidiary-branch
    --> HEAD -> main
    - here, references are shown.
      - HEAD is the commit that has been checked out in the local repository
      - 'main' is the commit at which the main branch in local repository points at
      - 'origin/main' is the commit to which the main branch in the *remote repository* (called 'origin') points 
      - 'name-of-subsidiary-branch' looks like a local branch, like 'main'
  - do you know why they are all grouped together, i.e.:
    ```
    --> (origin/main, origin/HEAD, name-of-subsidiary-branch) Merge pull request #21 from Karinaovedal/new_branch
    ```
    - because while they are all references named in different ways, they refer to the same commit.
    - --> what does 'references' mean here? and when you say 'checked out' earlier, do you mean like git checkout or switch, or something different?
      - references are: branches, HEAD, tags, and other things that point to commits (or similia). 
      - 'check out' is a bit of jargon, but yes, it means to use `git checkout` or `git switch` to change the content of the directory where the repository lives to match the state that was stored in a particular commit 

51. What is git remote -v --> like what is the difference here between fetch and push?
    origin	git@github.com:cr-workshop-exercises/recipe-book.git (fetch)
    origin	git@github.com:cr-workshop-exercises/recipe-book.git (push)
    - in this case no difference: both would relate to the same address. but it is possible to make them different.

52. What is remotes/origin/HEAD -> origin/main when running git branch --all?
    - it says that, on the remote repository, HEAD points to main.
        - what this means for GitHub: it means that main is the default branch there
          - That is my understanding but I am not sure

53. I "git clone https://github.com/networkx/networkx.git" the repository. When I enter `git branch -a` only main branch main is cloned. Other appears under `remotes/<branch name>`. I tried `git switch <branch_name>` it gives error `fatal: a branch is expected, got remote branch 'origin/v1.11'`.
    - you should try without `origin`, e.g. `git switch v1.11`. Then git will create a local branch called `v1.11` for you, and switch to it. Note that you can use `git checkout origin/v1.11` (which does not create a new branch), or just `git checkout v1.11` which does the same thing as `git switch v1.11`.

54. If i reference a commit hash when creating a branch for inspection, is there no chance this hash is existing already in another branch in the repo? And will the new branch be taken with the branch history/state as it was when that commit was done?
    - hashes do not exist in branches. A branch is a pointer to a commit, with the difference that while commits can't move, branches regularly change the commit they point to (typically, when you "create new commits on that branch"). Commits have parent commits and these relationships create a graph that can look more or less like a tree, and tree have branches, and that's why we use the "branch" term, but the analogy can be a little misleading.

## How to turn your project to a Git repo and share it
https://coderefinery.github.io/git-intro/sharing/

(but no problem to continue asking questions about previous topics)
    
55. Amazing music! :+1:

56. the somehash is not working it gives me the error message : "fatal: invalid reference: SOMEHASH^". What is this "somehash" made for / what is the function?
    - SOMEHASH is a placeholder for something like e25af5b that you see places: these identify the commits in the history.

57. Are there recommendations on licensing your code, pre- and post- publication, how does that work?
    - We actually have a lesson on this on day 4!  "Social coding"
    - Oh awesome, thank you

58. What is a track?
    - Like "GitHub", VSCode, "Command Line" - the options we have to do each exercise.

59. We will not do the section on git bisect? :+1:
    - We might do it at the end, if you ask.  We didn't have time to do everything.  We have video recordings of it beind done in the past.  (Ask again during the last part)

60. Let's say you have a project that you upload to GitHub while you're in the early stages of development. After a moment of "inspiration," you decide to reorganize the folders and code. Is it worth creating a new branch, or would it be better to just create a new Git project?
    - You can just commit the changes and push them on the main branch (unless you are not sure and want to keep the old code as the default version - in that case, use a new branch). Creating a new repository would mean to completely lose the history (it's ok if you intend to do that).
    
62. What about using Github cli? 
    - That can be used.  It is mainly for managing project metadata like making repos, issues, pull request, not the files within repositories (normal git does that)

63. Why have a license and which one is for what?
    - If you do not include a license to your code, nobody can reuse your code even if it is public. If you want to allow other people to reuse/extend your code, you need to tell them on which terms they are allowed to - that's what a license is for. It is particularly important, if you plan to collaborate with someone, that there is a license before the work starts or there might be arguments at some point (can I keep my changes private or must I share them? Can the code be used in commercial projects? Problems like these).
    - Okay, thanks! Arguments would be favorable to avoid:O

> https://github.com/bast/myproject

64. Please consider whether your source files contain passwords, credentials etc before uploading the files to a (public) repository.
    - Yes!  Very true
      - good point - I should have clarified 

65. If I make a private repository for my work, and I want to keep it private but release a version/tag and make that tag publicly accessible for the community while I continue to develop my work. How should I go ahead? Should I make a fork of a private repository? Is it possible to make a fork without the commit messages and other history private? How should I achieve this then?
    - When you release a tag in a git repository, it includes all past history.  (Just so you know)
    - You can develop locally, maybe syncing with your university's GitLab.  You then connect to a public repository on GitHub, and push there *only* the parts that are releasable.  `git push public-repo the-public-branch`.  It's normal to have different parts released in different places.

66. If I have binary files, or encrypted files, then the diff and change log is not available?
    - Correct.  By default it only can diff plain text files
    - But there are "git diff helpers" that can generate diffs of other files.
      - search for `difftool` and your data type on your favourite search engine. You can find difftools for many data formats, jupyter notebooks, latex files, and also specific syntax-aware tools for specific programming languages (if the output of git diff is not good enough even for text files).

67. How to configure my repository to have multiple remote repositories? For instance, if I want to use github and my university gitlab as remote repositories?
    - The `git remote` subcommand can add multiple remotes.  for example `git remote add public git@github.com/myuser/repo.git`.  You need to be careful about what gets pushed where, I recommend reading more.  It's not that hard though. :+1:

68. Do you recommend to use GitHub for creating repos, is that noticeably easier than using git locally, then pushing (?) up to github in some way?
    - if you know how to create a git repo locally, I would create it locally and then push it to GitHub (and in this case create a new repo there without README and without LICENSE otherwise there is a different commit there). reason: then the repo is on github and also on your harddrive and you don't need to clone and remove your old project (that was not git repo)
        - In the instructions it does not show how to do it, only how to push to a repo already created on GitHub? 
          - If you have already a local repository, you may have to do something along these lines:
            - create an empty repository on GitHub
            - note down the url 
            - add the remote repository to the local one with `git remote add origin <url-from-github>`
            - `git push origin`


### Exercise (instructors will resume xx:40)

https://coderefinery.github.io/git-intro/sharing/#exercise

Goals:
- Create a new directory called myproject with one or few files in it. This represents our own project. It is not yet a Git repository. You can try that with your own project or use a simple placeholder example.
- Turn this new directory into a Git repository.
- Share this repository on GitHub (or GitLab, since it really works the same).

Bonus:
- If too much time and too little to do, you can try to make some change to your project after you published it and publish also that change as a new commit.

How is it going?
- done: :+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1:
- not trying:o
- had major problems:
- wish we had more time:
- Struggling: o


69. I can't find the page you are currently looking at
    - Nevermind, I just realized that for each day there are two links. In my case I was clicking on "Introduction to version control with Git - part 4/4" which leads to https://coderefinery.github.io/git-intro/ but I would expect to end up on the right topic page (in this case https://coderefinery.github.io/git-intro/sharing/)
    - There is a sub-link on a lower line "Sharing work" - we should improve this.
    - Not a major issue but one can not easily distinguish that two independent hotlinks are there..to add to that, it seems that having https://coderefinery.github.io/git-intro/ on each daily link is redundant. Wouldn't one want to end up at the specific topic page whenever a specific day is selected? 

70. I created a new repository on github, than try to push my local folder from terminal. The command "git push -u origin main" returns the following error, and couldn't seem to resolve it: ![](https:![](https://notes.coderefinery.org/uploads/e789f9c3-0dc2-44ab-b4d7-e165a3c765f7.png)
      - I think what happened is this: on GitHub you selected that you want a README and it created a commit for you. now the commit history on github is different than the commit history locally.
        - easy but not-elegant recovery: I would remove the github repo and create it again, without selecting README or license (to not create any new unrelated commits there) and try to publish your local repo again. :+1: 
        - it is possible to also force git to overwrite the github history with your local history :+1:

71. How can you remove a `remote origin` that you created or modify it?
    - `git remote` subcommands can do this.
    - `git remote set-url origin NEW_URL`
    - `git config --edit` will pop up all config in an editor if that helps you.
    - `git remote remove origin` will remove origin.
    - Thanks!

72. I have a problem when i want to push from an existing repository into the command line, it says that the authetification failed, what can I do about it ?
    - are you authenticating with the SSH protocol? if yes, have you set up SSH keys? more info here: https://coderefinery.github.io/git-intro/configuration/#authenticating-to-github-ssh-or-https-or-vs-code
    - i think i fixed it, thank you

73. When you have your repository cloned locally on different computers, is it a good idea to synchronize the project folder between the different computers using rsync for example? or one should just synchronize always from the github repository? I'm thinking for example in my laptop and desk computer
    - I would always sync from the web platform.  I wouldn't recommend combing git with non-git syncing like rsync.  (If needed you can set up to push/pull directly between your computers)
    - Are we learning how to use push and pull later today?
        - more about push and pull tomorrow. today we only want to know that it exists as a mechanism to synchronize changes between repository. and indeed I would also synchronize changes from computer 1 to computer 2 by pushing from computer 1 to github and pulling from computer 2. additional sync tools can get confused by git metadata inside .git folder.
    - I see, thank you so much for clarifying!

74. I did the command line version. After making directory in my computer, I made it in github. When I tried to push my local repository to github ("git push -u origin main"). I received an error "fatal: 'git@github.com/USER/myproject.git' does not appear to be a git repository". UPDATE! I finally managed to solve it. I don't exactly know how, but I deleted the origin and started from beginning. Also had hard time setting up ssh rsa key. After the key was set, the push succeeded.
    - Is `myproject` the name you've made on Github? Self-update: yes it seems to be.  Hm...
    - maybe network problem temporarily? try again? same issue?

75. When I do `git add new-file.md` I often get this warning message `warning: in the working copy of 'README.md', LF will be replaced by CRLF the next time Git touches it` when I do `git add` and was wondering what it means exactly?
    - This somehow has something to do with line endings and Windows/Mac/Linux conventions... let me see what I can find
    - This might be relevant: https://coderefinery.github.io/installation/git-in-terminal/#step-4-two-more-settings-for-windows-only (thanks, it does remove the message, I'll look into it later)

76. I want to do this exercise in VScode. Do I have to create the project in github first, and then create a repo, before going into VScode?
    - no, VS Code can create the GitHub project for you so you can create it locally and publish it to GitHub without doing anything on GitHub first

77. When adding the remote origin to my folder with git remote add origin, does it have to gave the .git file? I get the error message "fatal: not a git repository (or any of the parent directories): .git"
    - Yeah: you need to `git init` first in the local directory you made.  This makes the `.git` dir which is used by git to track everything.
        - Is it okay if the name of the branch is "master"? Or does github expect "main"
        - Anything works.

78. :microphone: What it the proper way to delete a git folder?.
    - From the terminal this would work: `rm -rf .git` - warning, make sure you are in the right place
    - But you can delete it from a file browser too, it doesn't affect any files that aren't in there (you do lose all the history, if it's not synced somewhere else.)
    - Stream discussion: what is the .git folder?

79. Does the folder have to be empty when initializing it with "git init"?
    - No, it can already have files you have started.  This is also pretty normal.  `git init` alone doesn't affect existing files.

## How much Git is necessary? Where to start
https://coderefinery.github.io/git-intro/level/

80. After setting the remote origin, will "git push" be defaulting to "git push origin main"?
    - The branch also needs to know what is "upstream" (what it is "tracking").  In `git push -u origin main`, the `-u` means "remember this as upstream" and from then on `git push` alone will be equivalent.
        - Does upstream mean that it connects to the repo's github server?

81. Do commit messages support utf-8. For instance if I want use git for non-English language content?
    - I think so yes.  I use arrows like → and there are emojis there.

82. Can you elaborate on branch and tag. Why is tag necessary when you can save it in a different branch?
    - A branch can change, a tag can't change (unless you really try hard).
    - For example tags are used to tag releases: the release never changes, when it's updated you give it a new release number.

83. Is it a good practice to commit broken code just to save it and pick it up the next day?
    - If it's only me: I might commit to main just to save time, but others would say this isnt' good practice
    - If there are more people on it: you could make a separate branch to develop on it.

:::info
### Break (we return at xx:07)
:::
84. :microphone: Can you explain again which is the difference between Git and GitHun (or GitLab)?
    - (good question for stream) git: tool that creates and tracks commit. github/gitlab: web interface with the git repository underneath. in addition it implements "issues" and discussions. so look at GitHub/GitLab as something that is around Git.
    - note that one can push and pull and use remotes also fully outside GitHub/GitLab. you could have your own remote repository. but then nobody can possibly find it.

85. I am confused on how to differentiate between my github and gitlab account in the terminal. No really regarding the repository, more regarding my name and password. But mayve I should see $git as a third account.
    - you mean where a repository came from? (was cloned from?)
    - yes. you have an account on GitHub and another one on GitLab. Git itself is a tool/program that you can use independently locally on your computer and there is not really an account. But your local Git has configuration (you tell it your name and email address which ends up in the git log metadata)
    - `git remote -v` will show details of where it comes from: the URL will say github, gitlab, or whatever else.

86. :microphone: Proposed topics for after the break
    - Review again, what is Git vs GitHub vs GitLab now that we have seen a lot
    - Review again the difference between the GitHub, VSCode, and command line tracks, and how they relate
        - GitHub is good for showing concepts and things like inspecting and reviewing.
        - VSCode is a good balance of being able to work locally and being easy to use
        - Command line is most basic, you can do anything, but is hard to set up.
        - Most people combine parts of them all.
    - (git-bisect to demonstrate command line for everyone, discuss why it's there)



## What to avoid
https://coderefinery.github.io/git-intro/what-to-avoid/

87. Is it possible to combine multiple .gitignores automatically? For instance, if I have shell scripts with python code?
    - You'd copy the lines from each together into one file

88. What about adding generated files from for example conda environment files, that are used to run the code, is that also not recommended?
    - Do you mean like environment.yml?
        - Yes, like environment.yml
    - Did you make it yourself or was it generated?
    - I would often start with a generated one, but then manually fix it up and start treating it as a manual file.
    - I think the point about generated files in the materials relates to "generated by the rest of the code that you store in the repository", for environment files, this is actually later the file that you will use to generate your environment, so good to add to the repository and also track (versions of packages may change etc); more on environment files also next weeks Tuesday. 

89. Are there recommendations on how to connect versions of large files from for example Office365, with versions of the code in git? So that one can avoid putting large files in git
    - Hmm, there is [Git LFS](https://git-lfs.com/) and [git annex](https://git-annex.branchable.com/)
    - Both can support storing large files outside of the git repository and providing a way to download and get them. Or, you could write scripts, or tell people how to download them separately. Once you get here things can get advanced/complicated so I'd recommend a consultation with someone to design what works best for your case.

## Feedback and news

Day 2 news:
- We covered all of the parts listed in the schedule
- Tomorrow, we begin collaborative: we *all* work together to make our recipe book.  The same book, at the same time!
- What you need to do to prepare
    - It is possible to do everything on Github
    - But it's a good chance to work locally, if you have VS Code set up or command line.  We recommend a team to help here, since we can't help if it's not set up yet.
    - If you have a local team, you *can work together* instead of contributing to our example repos.


Today was:
- too fast: :+1: :+1: :+1: :+1: :+1:
- too slow: :+1::+1::+1:
- right speed: :+1: :+1: :+1::+1::+1::+1::+1::+1::+1::+1::+1:
- too advanced:
- too basic: :+1:
- right level: :+1::+1::+1::+1::+1::+1:
- needed more exercise time: :+1: :+1: :+1:
- needed less exercise time: :+1: :+1:
- I will use what I learned today: :+1::+1::+1: :+1::+1::+1::+1::+1::+1: :+1::+1::+1::+1::+1::+1::+1::+1:
- I would recommend today to others: :+1::+1: :+1::+1: :+1::+1::+1::+1::+1::+1::+1:
- I would not recommend today to others: 
- too slow sometimes, too fast other times::+1: 

One good thing about today:
- Kudos to the participants for sharing nice resources and links.
- The bad commit (whatthecommit) was funny
- I think the live demonstration are good (especially on command line) :+1:
- Sharing of best practices/pitfalls :+1::+1:
- Great that you showed the command lines 
- Today translated more "practically" to what you expect to get from the course than yesterday :+1:
- Inclusion of R Studio path, I will try it later :-) :+1:
    - See also https://happygitwithr.com/ :+1::+1:


One thing to improve for next time:

- Bisect exercise text can be improved :+1::+1::+1::+1:
- Bisect look interesting, but i tottaly didnt get it today 
- If one worked from VSCode/command line yesterday it was a little bit of repetition
- No cats today  :disappointed: :+1::+1::disappointed:
- Would be nice to hear more about git bisect +1

What part of the course format do you most (+) value and doesnt' matter for you (-)? (multi-answer):
- Topics: +:+1:++
- Being live instead of recorded: :+1::+1::+1::+1::+1:+:+1:+1:+1::+1::+1:
- Notes for Q&A:+ +:+1:++
- Written materials: ++++:+1:+
- Instructor explanations: ++ :+1:++:+1::+1:+1::+1:
- Video published: +++
- (+)Interactive learning, with the exercises as well as live lecture. Just like a classroom, and this helps learning.++++++
- It's great to be live so we all follow and ask questions here at the same time. :+1::+1::+1:
- Exercises: :+1::+1::+1:

Any other feedback?
- I commented earlier on the schedule page: Not a major issue but one can not easily distinguish that two independent hotlinks are there…to add to that, it seems that having https://coderefinery.github.io/git-intro/ on each daily link is redundant. Wouldn’t one want to end up at the specific topic page whenever a specific part is selected?
- Navigating to the right section on the materials website is tricky, too many links. It's actually easier to download as PDF to get it all expanded and use ctrl+f.
- Navigating to the right section on the materials website would be easier if the corresponding link is put on collaborative notes at the relevant time. This was done more often on Zoom, but there are some who are not on Zoom and they may find this helpful.
- It is not always clear which section of the materials is currently discussed on the stream. Repeatedly I had to go through several links and compare to the address on the stream..
- Thanks for today! Very useful :blush:
