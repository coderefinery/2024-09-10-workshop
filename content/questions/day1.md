+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 1"
+++

# Day 1 - 10/09/2024

## Icebreakers
Let's test the notes with some icebreakers! :icecream: 

### Where are you connecting from? How is the weather there?
- Kiruna, Sweden - Almost raining, not yet.
- stockholm, sweden - Cloudy and almost raining.
- KTH, Stockholm, Sweden - rainy and grey
- Gothenburg, Sweden - cloudy
- rainy
- Tromso, relatively warm, cloudy
- Helsinki, a bit cooler but still good by my standards +2
- Trondheim. Rainy as usual. +4
- Sunny Tartu +3 beautiful weather in Tartu today
- Espoo, cloudy but warm :sun_with_face: Windy :+1: 
- Oslo, sunny :)
- San Sebastián, cold and cloudy//x2
- Bergen, NO,  amazingly, not raining :+1:
- Copenhagen, sunny and not too cold
- Tallinn, Sunny
- Tromsø, the weather is shit as als 
- Bergen, NO, some sun, some drizzle, 12 degree Celsius
- Santander (Spain), cloudy +1
- Helsinki, relatively warm, cloudy
- Tampere, sunny and warm
- Espoo, sunny and warm +1
- Bucharest, cloudy
- Melbourne, sunny and cool
- Oslo and sunny!
- Bordeaux, cloudy!oooooooooo
- I am to believe I am sitting on an island with my laptop ... Iceland? Nope, island ... somewhere close to Alvar allon puisto ...XD cool ... Cool ? May be ... 
- University of Oulu, Finland
- kannelmäki
- Nesodden, Norway, sunny :heart_eyes_cat:
- Tuebingen, rainy
- Portugal, foggy
- Vaasa, cloudy
- Berlin, rainy
- Berlin, cloudy 
- São Paulo, in a heatwave 4 am.
- Helsinki, Nice weather :+1: :+1: :+1: 
- California, heat wave
- From the country side of France, cloudy and rainy 
- Trondheim, Norway! Grey and rainy...
- Berlin, rainy
- Helsinki, nice
- Patras, Greece rainy 24C
- Bilbao, quite rainy :)
- Oslo, Norway, great weather, 20C and sunny
- Helsinki, very windy!
- Stockholm! Cloudy, bit rainy, humid, sad :'(
- Stockholm, a bit rainy
- Lund, sunny
- Aalborg, a bit cold but sunny
- Edinburgh, Windy but sunny!
- Tampere, not sure
- Tonsberg, Norway, sunny 14 C
- Lund, Sweden, cold and sunny
- Vilnius, Lithuania, feels like summer!
- Trondheim, Cold and Raining: perfect weather :-)


### Have you used git before, if yes, how?
*Poll: Add an 'o' to the answer that applies to you*

- Don't know what git is: ooooooo
- Yes: oooooooooooooooooooooooooooooooo
- No: ooooooooooooooooo
- Yes: learned a bit on-line, but never implemented in my research ooo
- Yes, YT videos :) 
- Yes, on a programming course by myself, but never actually used it in a team setting
- No
- Yes, but I only installed as part of other tools. I don't know exactly what it is. o
- "Indirectly" through GitHub Desktop app
- Yes
- Only cloning repos :+1::+1:
- Yes, managing code till it becomes a mess
- just push and pull of main or master branch to keep track of latex documents and lately also some coding ( R ), would like to learn more +1
- No, I started to use it but only few commands :+1: 
- yes, just a little
- No, only Github
- A Little bit :+1::+1: :+1: 
- Yes, but only the basics.
- Yes, but only web browser version +1
- I have touched upon it, but knowledge is limited
- Nope
- Yes
- A little
- NO :()
- No, just GitHub but it was a few years ago
- Yes, a decent understanding but without team use
- Yes but not really from terminal
- Yes
- Noo
- a little bit but didn't really understand it - hence the course :)
- noo
- No
- I pushed my code to different repos, solve code conflict
- I have updated repos via ssh (commit on main branch), and rebased once, but not more
- Yes, started using it past week.


## Welcome and introduction

Materials: https://github.com/coderefinery/workshop-intro/blob/master/livestream.md

(always write new questions at the bottom, wherever that is - that's what we follow.  you can ask anytime, even now)

> Videos are also downloadable without YouTube (but requires git-annex, we should make that easier...): https://github.com/coderefinery/video-processing
> You can sign up for the github student package for freebies.


## Git-intro
https://coderefinery.github.io/git-intro/


1. Are there alternatives to git?
    - see question 3
    - Just to clarify, where can I find "question 3"?
       - Yeah, numbers get off here.  Down below.
       - As there is a lot of information on all your pages, I tend to search – in this case for "question 3" (find / cmd+f). It was not clear to me that Motivation 1., 2., .. was equivalent to question 1, question 2, etc.
       - Ah sorry, I meant question 3 here in notes (which you can find below)
   - mercurial is one alternative
   - also subversion is an alternative but very few projects use it
   - see also https://coderefinery.github.io/git-intro/motivation/#why-git-and-not-another-tool



### Motivation
https://coderefinery.github.io/git-intro/motivation/

2. Whats the difference between Git and Github?
   - Git is a program and repository format.  GitHub is one web service that uses it.  GitHub is like Gitlab, Bitbucket, etc.
   - Like: .mp3 vs Spotify?  There are many programs that make and read mp3s, mp3 is name of file format, Spotify is one service that hosts it.

3. What makes git different from other version control systems like cvs and mercurial?
    - Fundamentally, they serve the same purpose quite (as much as this lesson goes into)
    - Git is relatively modern so it is fully distributed: every repo is its own copy.  This allows it to be used by larger groups and more socially than others could be (we'll see this in day 3).  But these aren't unique to Git.

4. I do CFD simulation, where the files are couple of hundred of GB. How do I manage different versions of the simulation files. What is the best way in your opinion? Thanks :).
    - I'd say: for big files like this, you probably want to track them separately (they are big enough you need a dedicated version management system)
    - I (one of the insturctors) like tho tool git-annex but it is rather hard to use.  It is good at big files and you can control where each file is stored.
    - The normal problem with big files is that every copy of the repo has every file, so big files makes lots of wasted space.  This is what git-annex (and git-lfs) tracks.
    - I would add: keep code and large datasets separated, because if I have to work on your code I would not like to have to download several GBs of data just to look at your code. Moreover, does the data need to be version controlled with the code? Perhaps yes, but then it's better to add some metadata in the data files pointing at the version of the code used to produce the data (e.g., a git tag or a git commit). 
    
5. Can you explain a potential word processing software that can be tracked by Git? I ask b/c I am not sure MS Word is compatible.
    - latex, try it on overleaf for example if you don't want to install anything. 
        - Overleaf officially has very good integration with git/gitlab/github
    - markdown, basically everything that is a text file.
    - Any files, including Word, can be tracked with git.  The merging that we just talked about can't be done with Word files automatically.  (It still might be worth it though: I sometimes use git in these cases just to have the version history)
    - For collaborative document editing, I personally use either latex with overleaf (if everyone is fine with it, since latex is very different to what you see is what you get editors like word), or I use google docs or similar online tools, which also do some version tracking if you activate it. 
    - I'd like to recommend Markdown also, for it is compatible among many tools, as Rstudio, Github etc.
    
6. Follow up to Q4 and Q5. Which types of files can be managed using git? And for which types of files should git be avoided (if possible)? 
   - Any file can be *tracked* in Git.  (really big files not recommended)
   - Only plain text files can be *diffed* and *merged* automatically in Git: code, LaTeX, text files, small text data files, conf files, etc.
   - There are extensions that allow *diffing* *merging* of other files like Jupyter notebooks.
       - :+1: 

### Copy and browse an existing project
https://coderefinery.github.io/git-intro/motivation/

Example repo: https://github.com/cr-workshop-exercises/recipe-book
Example repo which will be shown on stream (your names will be recorded and on YouTube): https://github.com/cr-workshop-exercises/recipe-book-recorded

7. What is the difference between forking and cloning a repo?
    - Cloning creates a local copy of the repository to you machine. Forking creates a new representation of the repository in the online repository network associated with your account.  

8. So follow up to question 7, forking is specific to the online repo only, and cloning only copies the repo from a remote repo to your local machine?
    - Forking is an operation that takes place on GitHub, GitLab and so on. It's like cloning - but on their servers - with some additional information attached. Cloning instead is a more fundamental operation, that is copying a repository (typically, but not only, to your machine) while also remembering the source (git will know the "origin" of the repo once you have cloned it).
    - BTW, when using *git clone*, the local copy of repository will NOT update automatically. You need to use *git pull* for updating. 


9. Is there a/any convention for labeling commit messages?
    - First line is quick summary of what happened (often imperative statement).  Then blank line and then longer description as needed.  For small projects doesn't matter so much, larger ones may have standards.
    - See this example for a convention https://www.conventionalcommits.org/en/v1.0.0-beta.2/

10. Trying to search something, what does "This repository's code is being indexed right now. Try again in a few minutes." mean?
    - It typically means that the repository is in the process of having its code scanned and indexed by the platform (such as GitHub, GitLab, or similar) to make it searchable. Once the indexing is done, you can search through the repository.

11. What is the best way to see pull requests from command line? Can you see the pull requests made in a clone of the repository you have forked -- for instance in a clone of my fork of the recipies directory `https://github.com/<USER>/recipe-book` can I see the pull requests made to the original repo? Can you see a pull request if in repositories that you have cloned repository -- if I clone the `https://github.com/cr-workshop-exercises/recipe-book repository?`
    - Pull Requsets are a GitHub-based concept.  Branches exist in git: you can clone the repo and look at what branches are there.  PRs can only be seen in the GitHub web interface, or `gh` command line tool, or other similar things. :+1:

### Exercise until xx:10
https://coderefinery.github.io/git-intro/browsing/#exercise

- You are pretending to be a new person joining a project.  Look through the repository and understand what the current state is
- Try to do what you can, but if you can't do it all, it's OK: you can still continue
- Ask questions below as you keep working on it.

Poll: You are:
- Done: oooooooooooooooooooooooooo
- Not doing exercise: oo
- Major technical issues: o
- Don't know what to do: oo
    - Read: https://coderefinery.github.io/git-intro/browsing/#exercise and do as much as you can; ask questions below if something is unclear

More questions: 
10. I cannot find the commit history. I am on github <>Code
    - on github? it's the little clock icon top-right-ish, below the green "<> Code" button. in my case: clock icon with "32 commits" next to it
    - Got it, thanks
    - I don't find this clock icon (there should be a snapshot in the lectures) -hint: I am another person)![](https://notes.coderefinery.org/uploads/b7704bc7-a4e9-44af-85fe-1ebcb9bb29f0.png)
    - thank you for highlighting it, this made the difference :+1:
        - You're welcome :)
        - and good suggestion to add a screenshot. later we will learn how everybody can contribute changes to any repo, also our lessons :-)
    
11. I forked the main branch of the exercise repository. Is there a way to "un-fork" and fork all branches?
    - you could delete the fork (settings and scroll all the way down) and re-fork, but it's not a problem for this or other exercises. if you want to browse the branches, you can also do it in the original repo that you forked from. 
    - Settings-> Danger zone towards the bottom -> "Delete this repository"?
    - but don't worry about it since only branch labels are gone but the network is still there (this will become clearer later what branch labels are)


12. I am trying step 5, searching salt,  but I get an error message `This repository's code is being indexed right now. Try agagain in a few minutes.`
    - Wait a minute for index to be made, and it should work.  We hope.
    - I tried this: repo:username/recipe-book "salt" but also got an error with it saying it is indexing ^^
    - I got exactly the same error. wait for a while, still doesn't work. any way to manually index?
    - At least it work if you try repo:cr-workshop-exercises/recipe-book salt
    - Update: Now is working.
    - It works on the original repo, but not on the repository that I forked, is it just a question of waiting some process to finish?

14. I cannot find "Insights" question 2. 
    - "Insights" is on top of the page, above the green button, found it?
    - Got it, thanks. It was hidden under ... because the window was too narrow
         - ah!

15. How to add search term to “repo:USER/recipe-book” ?
    - Add a space there and extre term in the box (I think)
       - yes, on top of the page there is "(magnifying glass) Type ..."

16. Do i need to write down these excersises somewhere in order to get the accredited?
    - I recommend to not delete the fork that you created until the credits are approved. In next exercises we will start to make changes to the forks.

17. I went to the pull requests tab but don't see any.. is that the issue for other people?
    - I see atleast two pull requests. Did you visit [here](https://github.com/cr-workshop-exercises/recipe-book-recorded/pulls)? 
    - Maybe you look at the pull requests to your fork (and there are possibly zero). But try to browse the link above. We did not explain yet what pull requests are but we will get there.
    - I checked and there are no pull requests in my forked version, but there are 2 where you mentioned, and 1 for teh recipe-book rep (not recorded), so maybe it has to do with my fork not bringing over the pull requests?
    - Yeah, the pull requests would be only on the first repo,

### Break until xx:21
- Then a bit of commentary on the exercises


19. What's the different between GitHub, VS Code and Command line?
    - They are all ways to look at the same repo data: basically, different ways of working.  Most people would use "command line" or "VS Code" for daily work, but GitHub web interface is good for simple things
    - We offer three tracks to make it easy for people at any level to follow along and understand the concepts, without having to learn some new tool.
    - 
20. The network looks different when using the forked repo, as opposed to how it looks in bast's repo (extra long line is added to the graph for my user in my forked one)
    - we'll need to investigate some.  It does look a bit different than I expect, since it doesn't show the main repo.

21. What does it means that a branch is merged into the main branch?
    - We'll learn more about this tomorrow!
    - Basically: two lines of work come together and get combined.

22. Do you count the initial commit as a change?
    - Very insightful question!
    - For git: yes it is a change, same as anything else, it adds new files. (under the hood, git doesn't actually track changes, it tracks versions.  It's the first version, if you ask to show changes it shows everything.)

23. Why in the network graph appears several labels of main?
    - each repo in the "fork network" can have its own branches.  Is there only one per row with a username? (yes)

24. If I click "blame" view and then click on "blame prior to change" I visualize the code before the change, correct? But how to reverse it? How to come back to the code after the change was made? I can't undo this, unless I go back to the main repository and click again to open the code.
    - interesting! I did not know about the nice functionality "blame prior to change" - only way I know to get back is to click back on the repo and reload it

25. Does it take a while for the network graph to display? It seems it has been rendering for a while. 
    - For me it is taking forever too...
    - Good it's not just me :)

26. How do I change folder of a new recipe?
    - great question! I am not sure this is easy/possible on GitHub. For this I would go to the command line where one can "git mv oldfolder newfolder". Anyone else knows how to do this on GitHub?

27. Do the releases i.e., 'tags', are basically assigned to the most recent or all the commits prior to that in said branch, in this case, the main branch?
    - They are assigned to a single commit (you can specify an older one though).  Because of how Git works it includes all the previous history.

28. Is there the same functionality for 'compare' repos in GitLab? If so, can you just compare two text files from within each repo?
    - Yes.  For two different files, I don't know if that can be done via the web.

> More questions below exercise

### Comitting (recording) changes
https://coderefinery.github.io/git-intro/commits/

#### Exercise: Recording changes (making commits), until xx:55
https://coderefinery.github.io/git-intro/commits/#exercise

- You pretend to be a new contributor: you make a branch and add some changes, separate from the "main" branch
- You then do another change on the main branch
- You see what this looks like: how all the commits go together.
- Try to get to at least step 2 or 3 to be able to do the rest of the day.

Poll:
- I'm done: oooooooooooooooooo
- I'm not trying: o
- Had major problems: oo


25. How to add a folder?
    - You'd add a file in the folder and folder made automatically (git doesn't track folders...).  (Note: can you add a file in a new folder in the Git web interface?)
    - yes, on github create a new file (plus symbol), then start typing "somefolder/" and this then suggests creating the folder.
    - I can add a new Repository, gitspace and gist. Which one is a new file? 
       - it's the plus symbol left of the green "<> Code" button to add files/directories. the plus symbol on top of page is for something else.

26. How to create a branch without switching to the branch (from command line)? And how to switch to a branch that has been created?
    - `git branch BRANCH-NAME` makes it from your current location
    - `git branch BRANCH-NAME STARTING-POINT` makes it from STARTING-POINT.

27. How to know the branch that is being modified (vs code)? For instance, how do I know which is the branch to which I am committing?
    - Are you on command line, vs code, or Github?
    - VS Code: I think you see it on the bottom left corner.
    - This is a *very* good question: one should always know what branch they are before commiting!

28. How does the food service look like at Aalto?
    - Are you in the meeting room?
    - No but I'm thinking if I should come over tomorrow.
        - There are cookies and coffee :)
        - Lunch is self-paid in the building
            - OK, sounds good. Will be there tomorrow.

29. in my network graph I can see other users. do I have to opt in/out something to make them invisible?
    - You can make repositories and forks private which should hide them from these things
    - Github public repos are designed for collaborative projects, thus things are very open and linked ("Social Coding" is their tagline).  These days you have have free private repositories.

30. VS code asks me to publish my branch (while pushing). What does it mean to publish a branch? It says branch `branch-name` has no remote branch. Would you like to publish the branch.
    - Someone who knows vscode better should answer, but: I think it might mean "do push outside the first time"
    - making the branch visible outside your computer by "pushing" it to the remote repository (we will clarify "pushing" and "remote" more on Thursday)

31. Scenario: The contributor of a project forks the main repository, then creates a feature branch in his forked repository. While the contributor works on his feature branch, changes are made to the upstream repository. The main branch of the forked repository has the main of the original repository as upstream and can be updated quickly, but then the feature branch in the forked repository is missing the new changes made to the main repository. Therefore, the main in the forked repository must be merged into the feature branch. Question 1: Should one merge or rebase? In general, is it better to merge or to rebase? Why? Question 2: If changes in the feature branch conflict with newer changes pulled from the upstream, a conflict will arise. What is the best practice at this point?
    - we will discuss conflict resolution later. rebase will make it look like the local branch commits happened after the upstream commits. advantage: nicer history. disadvantage: conflict resolution can look a bit tricker for a conflicting rebase compared to a conflicting merge.
    - My practices: question 1: rebase if it's simple and it's only me working on it.  Otherwise merging (looks worse but saves frustration).  We'll talk about question 2 tomorrow or day 3.
    - Personal opinion: 1. Rebase gives you a nicer commit history, without the need of merge commits. Of course rebasing is ok only if you know what you are doing (i.e., rewriting history of the rebased branch - it can be rude if you have already published that branch). 2. Conflicts happen, it's a fact of software development and tooling against this can help you much less than using proper practices (e.g., merge/rebase very often, and use CI/automated tests every time to be as sure as reasonably possible that you're not breaking anything)

32. I get the error "We weren’t able to create the release for you. Make sure you have a valid tag. " when I want to create a release. My tag name is "inventing-potato-salad". what is wrong with it?
    - Hm, I'm not sure.  
    - we will try to reproduce the problem. can you post exact steps that lead to this?
        - hei, I asked the question. I think it was because of the tag I wanted to create. It had spaces. I tried again without spaces and it worked.

33. What are the 'tags' exactly? When do you use them?
    - It's used to record one point in history which (in theory) will never change.  To record milestones like releases or paper submissions (which might be updated but then it gets a new tag)
    - they make it easier in papers to refer to a version. instead of saying that this paper was generated with commit abc123xyz456... (hard to remember), you can then say that this was version "v1.1" which then resolves internally to abc123xyz456...

34. Are tags given only to the main branch? Or is it possible to add tags in other branches?
    - Anywhere
    - it is also possible to add tags to past commits

35. Can you explain a bit that "timeline"? Is it minutes, or arbitrary x-axis?
    - Arbitrary units: I think they essentially make all intervals a unit of one while keeping teh order
    - commits are chronologically ordered but I am not sure the timeline is linear. the key here is the ordering.

36. Can you show the compare function again? A bit fast. And your pictures hide the URL on top
    - We'll try to show again but here is the URL you get to it: https://coderefinery.github.io/git-intro/commits/#compare-two-arbitrary-commits
    - Got it, thanks

37. A bit off-topic license question. You license your repository under a CC0 license. I think that this works for the recipes (as they can be equated to data), but I am not so sure whether this can cover the python recipe-checker.To my knowledge CC-XZY licenses do not really apply to code as they do not cover the liability issues that are potentially linked to re-using code. But I stand to be contradicted and would like to know the reasoning behind your choice.
    - very good remark (we added the script later). for the script a good license choice might be BSD or MIT. for a repo that has both data and code one can add one license for data and one for code. we should have done that. more about that next Tue but here we only wanted to raise awareness about licenses and derivative work and reuse. but great observation!

38. In the "(5) Browse the commits you just made" for VS Code you mention it requires and extension, do you know which one it is exactly?

## BREAK until xx:00
Please keep asking questions below, we will try to answer also all open questions asap


37. When I try to push my commit on the new branch (in the last exercise), I get the error message 
    ```
    ~/git/externals/recipe-book$ git push 
    fatal: The current branch butter-for-all has no upstream branch.
    To push the current branch and set the remote as  upstream, use
    
    git push --set-upstream origin butter-for-all
    ```
    I am hesitant to "set upstream origin" as I don't want to push to the upstream repo that I forked, but maybe that's not what will happen?
    - maybe you typed: "git push butter-for-all" instead of "git push origin butter-for-all"
        - I typed just "git push"
    - it will work if you type it explicitly: "git push where-to which-branch". the error means it did not know where to since the local branch wasn't connected to any upstream branch. if you type "git push --upstream origin butter-for-all", it gets connected and from there on you can type "git push" and it will know what you mean. but I recommend to be explicit about which branch and where to.
        - Ok, thanks! Do you recommend "git push butter-for-all" or "git push origin butter-for-all"?
          - I use the latter. It's a little bit more typing but more explicit but pushing a branch somewhere is a once-per-day/once-per-week operation so it's not too much. 

- 38. I have done two commits in my new branch, in a new file/recipe, then switched back to main again, and there I modified an existing recipe. When doing the git diff, I only see the new file in the new branch, not the changed text in the recipe I modified on main. Was I supposed to see that change I did in main as well? I can see all the changes on github, and they are showing nicely in the git log --graph output.
    - you compare with "git diff main new-branch"? yes, I would expect to see changes done on both branches. once this works you can also try the other way: "git diff new-branch main"
        - Ah, it does show, but it does not show the changed text, so I overlooked it. It was at the bottom (wished it would have shown what text was changed though):
        ```
        diff --git a/mains/vegetarian-lasagna.md b/mains/vegetarian-lasagna.md
        index 1a4d50b..b03ed8b 100644
        ```
        - does it show the changed text before the +++ --- data on top? it should show added lines and removed lines.
    - I have the same issue, however I am not using the terminal but the web interface. When I compare, I see the new recepie I created on the new branch, but not the modified recepie on 'main' branch.
    - We might have to look at this more later.  Do you have anyone local to show it to to ask for another opinion?
    - If I swap to compare the new branch with the main, not the other way around, than it shows both changes.
        - Do you mean swap order in the diff, or swap to the branch before diffing? When swapping order in the diff I still don't see it here.

- 39. Is there a way to synchronise between using VS code/GitHub/ the command line? I was trying to see if anything was different in my local folder, but the new branch didn't appear with "git status". I did the exercice on GitHub and was trying to see anything on my local computer.
    - VScode and command line: if you navigate to the same directory, you see the same repo.  You can use both in parallel
    - For GitHub it is cloning, pushing, and pulling... which we will talk about tomorrow.

- 40. How to check if I have cloned using HTTPS or SSH URL (from command line)?
    - Could it be `git remote -v`? :+1: 
        - If you did it by ssh it will show something like `origin git@github.com:coderefinery/repo.git (fetch)`, for https it will show something like `origin	https://github.com/coderefinery/repo.git (fetch)`


## Merging changes
https://coderefinery.github.io/git-intro/merging/

### Exercise until xx:35 : Merging branches 
https://coderefinery.github.io/git-intro/merging/#exercise

- This depends on having made some commits in the previous exercise - you go back if needed
- You will practice making a "pull request" (aka "change propsal")

Poll: I am:
- done: oooooooooooooooooooooooo
- not trying: o
- had problems: oo
- need more time: o

Please ask questions below :)



41. I created a brnch new-recipe, but it does not appear on github when I check in branches. IN the command line when I write git branch, it shows both the main and new-recipe branch
    - You need to push the changes...Hmm push has not been covered yet.
    - The exercise text has you do this merge only on your own computer (without a Pull Request on Github) since we haven't gotten there yet.  We're sorry, but all the pieces aren't there yet.  You can:
    - Try to push (`git push` or VSCode push) (but this is something new!  You don't have to)
    - Do the merge only on your computer like it says
    - Make a new commit on Github.

42. Do the releases i.e., 'tags', are basically assigned to the most recent or all the commits prior to that in said branch, in this case, the main branch?
    - you can decide which commit to tag. if you create a release/tag on github or if you tag locally, by default it is your current branch and current commit but you can tag commits in the past.
    - --> how do you tag certain commits in the past?


    - They are assigned to one commit (version) but because of how Git works that contains all previous versions, too.

43. Is there the same functionality for 'compare' repos in GitLab? If so, can you just compare two text files from within each repo?
    - I believe there is. Let me look it up ...
        - I just tested in on gitlab and same thing works there. if you add "/compare" at the end of URL it lets you compare branches or tags or versions. (if this was the question)
        - Yes, that was the question, kiitos.

44. When I try to make pull request it is warning me "Can't automatically merge. What should I do?"
    - Does it talk about a way to resolve the conflicts?  If so, then the same lines of the same file was modified on both sides (we'll demonstrate this after the next break).  In this case, I'd recommend making a new branch and commit to keep it simple.
    - Thank you, I'm trying with a new branch
    
45. I created the pull request and completed the merge on github. Now, on my computer how do I know that there are changes made to the main branch on github (on vs code and via command line)?
    - now you would need to "pull" the update to your local repository so that it shows up also on your local main branch. command line: "git switch main" (to make sure you are on the main branch) and then "git pull origin main" (pull the changes from origin and integrate them into my main branch)

46. When I merge "branch" with "main", I see the content of "branch" is inbedded in the "main", however the changes on "main" does not show up on "branch". Does this mean that the merge is only one directional?
    - yes, merge only modifies the branch you merge to, it does nothing to the other branch and keeps it unmodified.

47. What are the Squash and Rebase in the merge options?
    - good question! let's demo it later. but in short:
      - squash: combine several commits into one
      - rebase: is an alternative to merge where instead of creating a merge commit, the branch is moved "to the end", behind the other branch, incorporating the commits of the other branch.

48. When I accidently modified and committed changes to the main branch that were meant for another branch, is there a way to go back to the original branch and transfer changes, as to not lose the progress/changes made locally? Hope that makes sense..
    - the another branch already exists? or not yet?
    - the other branch exists but was not selected prior to making the changes (i.e. changes were done to the main branch but are supposed to be part of another branch)
    - this is not a complete answer but for command line we have a recovery chapter here: https://coderefinery.github.io/git-intro/recovering/#recovering-from-committing-to-the-wrong-branch
    - in short, the recovery would be: get the commit to the branch where it was supposed to be, and then rewinding the other branch back by one commit. I am not sure the latter is easy when purely on the web and personally I would fix this on the command line.

49. I merged the branch. But then after the merge, I made some changes to the branch I had created and then I did a commit and push on the branch `git push origin <branch-name>`. Should I see the new pull request for the changes I made on the branch automatically on github?
    - You should see the branch on GitHub, the pull request you'll have to create yourself. :+1: 
    - (Sometimes) GitHub shows a yellow box saying there have been changes on branch X, do you want to create pull request (or something along the lines)
    - You can always go via the pull request menu and manually choose the branches you want to create a pull request for 

50. When I try to merge using the command line it automatically opens vim for making a description of the merge. Can I make it open using nano, or is there another way that doesn't rely on vim?
    - Yes, you can set the editor: https://coderefinery.github.io/installation/editors/
    - roughly `git config --global core.editor EDITOR_COMMAND` - read to see the right way for each editor.

51. How do I un-commit a proposed change to a repository? 
    - the pull request is already merged or not yet?
    - not yet, I am not the owner of the repository (I forked the repository but accidently suggested changes to the original repository)
    - You can close the pull request.  Removing the branch is a separate thing which can be done (I don't think we cover it).

52. Just out of curiosity, in large projects with multiple people working on the same code, is it possible to merge multiple pull requests before sending to main?
    - The same way you merge different branches into main you could also merge different other branches into each other via pull requests; I'll let someone else comment when this is useful.
        - ...

53. Can we make pull requests for changes selectively?
    - Yes (but you need to make different branches for each change - a branch is the fundamental unit of work)

54. If I make a typo in the commit message, is there a way to correct it in the web version of GitHub?
    - I don't think so (from command line you can on your own computer, but that is "rewriting history" and we'll talk about risks of that later).
    - What could you then do in that case?
    - I'd just go on: commit messages are a log, not perfection, and doesn't really matter in the future.  (There are plenty of typos around).  I think it's better to commit often than try to be too perfect.
    - If you ask someone they can help you fix it via the command line if it was really important
    - no worries!
    
55. How do I know for sure that a branch can be safely deleted? Are there any specific checks that can be manually performed on the cli?
    - Normally most things that would delete a branch would warn if you are losing info
    - You can delete a merged branch, since the new branch (`main` here) now includes those commits: you aren't losing the data, only the pointer to that data

56. After removing a branch, can you recover an old version from that branch?
    - If it's merged in with something else: yes, look at the network and you can see *every* old commit, and figure out where it was.
    - I see, thank you!

57. If I have made multiple changes, for example added and modified files, to a fork but don't want to include all of them in the pull request, is it possible to choose/delete only some of the changes?
    - You'd need to separate it out into separate branches.  There are different ways to do this if it's already together.

58. How do I add the currently pulled request in the original repository to my fork of the recipe-book?
    - This is "updating the repository".  I think we talk about this somewhere, maybe someone has the link.

59. Can a person who hasn't forked the base repository make contributions?
    - No, you need the fork as a way to store your changes before they get accepted (since you can't modify the main one)
    - Unless you have been given permissions to modify the "upstream" - we'll cover this on day 3! Good question.

- 60. How does multiple people working on the same file commit and merge onto the same file of the same branch ? I can imagine things will get messy. What is the best practice to solve the isssue?
    - typically no problem if they are editing the file in different places but to avoid conflicts and surprises it can be good to inform others who are working on the same file. nice mechanisms for it: issue or draft pull request (or other communication). then conflicts might happen but we will resolve them.

- 61. Is there a way to rename a single file? +2
    - GitHub web: go to "edit this file view" and it looks like you can edit the filename there. 
      - Where is "edit this file view"? => You go to edit the file and then, the name of the file is editable (right at the top of the window with the contents of the file)
    - Local (command line/vscode): rename the file and add the new one / `git rm` the old one.  `git mv` does both at once.

### Break until xx:06
- Then we have a demo of "conflict resolution": what happens when two people modify the same file?


## (making and ) Resolving a conflict
+1
This is a discussion and demo-only (you can try it out later on your own) .

- 62. Not conflict based, and might come later, but how do you "update" your local main to reflect the forked original, i.e. so that the kebab recipe appears.
    - We'll see this tomororw.  it's "update"

- 63. Do you recommend using branches no matter how small the changes are, and no matter the size of the team (one person or several)? Doing branch, pull request and merge for small change when it is a small team seems maybe like a lot of overhead in admin?
    - It really depneds on the use case.  When you have multiple people actively involved, branches + pull requests keep everyone informed.

- 64. Can I retract a merge request? Lets say I changed my mind, or I noticed some problems.
    - Yes.  You can close the pull request.  After it's merged, you would undo the commits in new commits.

- 65. What kind of discussions should go into issues, and what should go into the discussion of the PR? The communication to solve a conflict seems like it fits in the PR, but for other things the line can be blurry...
    - Yeah, it really is blurry: often something starts in an issue and moves to a pull request.  You can refer them to each other.

- Kitty! :heart_eyes_cat: :+1: 
    - CATS

## Feedback, day 1


### News for day 1
- Today, we covered all the lessons as shown on the course page.
- Tomorrow, we will do many of the same things, but now on our own computers (and cloning/pushing/pulling between the web and your own computer) :+1:
- Tomorrow, having the local editors available is good: VS Code or command line.  If you don't have these, you can still attend and there are some steps you can do, and you'll learn for the future. :+1:
- Twitch will hold a reply immediately, for seven days.  They will be on YouTube by midnight.


Today was (vote for all that apply):
- too fast: :+1::+1:
- too slow: :+1:  :+1: 
- right speed: :+1: :+1: :+1: :+1::+1: :+1::+1: :+1: :+1: :+1:  :+1: :+1: :+1: :+1::+1: :+1: :+1: :+1::+1::+1: :+1::+1: :+1: 
- too advanced:
- too basic:
- right level: :+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1:
- needed more exercise time: :+1::+1:
- needed less exercise time: :+1: 
- I will use what I learned today: :+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1:
- I would recommend today to others: :+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1:
- I would not recommend today to others: 
- too slow sometimes, too fast other times: :+1::+1::+1::+1::+1:

One good thing about today:
- HedgeDoc is a nice way for interaction between participants. :+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1::+1:
- I really liked the rythm of the course, you do not assume we are git geeks :) :+1::+1::+1::+1::+1::+1:
- Breaks were enough.:+1::+1::+1::+1::+1::+1::+1::+1::+1::+1: 
- Nice course materials :+1::+1::+1::+1::+1::+1::+1::+1::+1: 
- Cute cat(s) :+1::+1::+1::+1::+1::+1::+1: 
- Clear explanation for the things we go:+1: 
- Great combination of interaction with the video + notes document + materials website + own work. I feel I learn the material quickly with this. :+1::+1::+1::+1:
- I like the communication with the masses through shared text :+1::+1::+1: (agree, particularly if you wanna go through the material again you can revisit the questions)
- Practical tasks, easy to understand, usefull for use in the near future
- HedgeDoc was nice, since often people leave their mic/video accidentally on on Zoom/Teams and  this causes interruptions. Now it was prevented, which was nice! :+1:

One thing to improve for next time:
- The concept of git push was not introduced properly. It is required to make sure that the commits made locally are seen on github. It would be nice if you could spend a few minutes to introduce git push and how to work with remote repos. We did a clone and just after clone was introduced, it would have been nice to introduce a git push with a git commit of a small change made to a file.  :+1::+1::+1::+1::+1::+1:
- I still feel a bit lost with how to integrate git or github within a writing a word document task, can i just upload a word document to github? 
- I dowloaded the tools you recommended, visual studio code, but we did not get info on what those are for :+1:
- It would be great to have a bit more time for the exercises (maybe not the last one with the pull request, but the first couple exercises). I found that I had made it through around 75% of the exercises before we returned to the session, so I would suggest and extra 5 - 10 minutes.:+1:
- Yes, agree with the last one, particularly if technical problems emerge, you need to time to resolve those problems first :+1:
- I would like to use VScode to talk to github/my local git but I miss the link -> need some assistance to transfer
- Perhaps 5 minutes about the BIG picture :+1::+1::+1::+1:
- As usually in real life git is used on commandline, it would be great to introduce also the instructions for that too :+1::+1::+1:
- I would like another way to communicate with the instructors maybe in addition to HedgeDoc for immediate issues, like the Zoom faces sometimes were on top of the web URL or blocking different features on GitHub, so if there was a way to communicate this more quickly, it would fix something relatively basic.
- I believe that the pace was too fast at the beginning, when I was still getting familiar with the basic interface. Afterwards it was OK for me :+1:
- If i get behind, I get lost easily.:+1:
- The git CLI examples don't always include all the steps needed, seems the GitHub website GUI is complete for all questions
- more cats!! :+1:
- Maybe you can all save a copy of this forum from today and email it to the course participants as a PDF? I suggest this especially as you mentioned that these notes can easily get deleted...
  - this notes should remain available and they are even version controlled. You can download them as HTML (or Markdown) from the Menu
- Will the notes remain available indefinitely?
    - They get archived on the course website indefinitely (cleared from here for tomorrow though)


Any other feedback?
- Thanks for today, super useful!!!! 
- See you tomorrow, thanks!

