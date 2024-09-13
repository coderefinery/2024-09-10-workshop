+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 3"
+++

# Day 3 - 12/09/2024

## Icebreakers

Let's test the notes with some icebreakers! :icecream: 

If you could ask for any superpowers, what would you ask for?
- Fly :+1: :+1: :+1: :+1: :+1::+1:
- teleporting (:+1:)
- Regeneration
- Blink (short-range teleport)
- Undistracted focus
- Becoming a cat
- Turning into a neutrino ...
- Breathing undewater
- Understanding women :( (s/women/humans)
- Wake up early

In preparation for today, have you opend an access request issue in [access request repo](https://github.com/cr-workshop-exercises/access-requests/issues)
- Yes and I accepted it:oooooooooooooooo
- Yes but I have not accepted it yet: 
- I did not sent it yet, but will do it asap: oo
- I do nt know what you mean, help me: 
- Yes but haven't gotten the email yet: o
- yes

---

## Questions from Day 2

1. Where are the notes from today?
    - You can find them all linked from the event web page: https://coderefinery.github.io/2024-09-10-workshop/questions/
    - Okay, thank you
    
2. Feel free to answer this tomorrow (12/9):
   ```
    git branch --all
        * alex/fruit-salad
          main
          test-banana
          test-cherry
          remotes/origin/HEAD -> origin/main
          remotes/origin/alex/fruit-salad
          remotes/origin/main
          remotes/origin/radovan/lasagna
          remotes/origin/radovan/poke
          remotes/origin/radovan/vegetable-soup
    ```
    --> I checked and the last commit was from Alex in March, so why does it say this:
        --> remotes/origin/HEAD -> origin/main
        what does this indicate? I thought the HEAD was the pointer to the latest commit, so I'm not sure why it is origin/main if the latest one was:
    ```    
        git log
            commit 89d5ef9b8296b57c29c734b7c5288a643e85eb8f (HEAD -> alex/fruit-salad, origin/alex/fruit-salad)
            Author: Alex Smith <alex.smith@example.org>
            Date:   Wed Mar 6 20:22:55 2024 +0100

            fruit salad: instructions
    ```
   - you are right that HEAD normally points to the current commit when working locally. GitHub uses HEAD to point to the default branch. From `remotes/origin/HEAD -> origin/main` I can see that `main` is the default branch on GitHub. It was a good question and it is a bit confusing and I believe here GitHub uses a Git feature to keep track of default branch.

3. git log -S fixme --> I tried this in the networkx repo and it returned several commits but didn't see the pattern of 'fixme' in those logs, why not?
    -- e.g., git log -S fixme
            commit 870ca9b9298f92323504c2bbf234618ac11256d4
            Author: aric <none@none>
            Date:   Tue Aug 11 17:36:07 2009 +0000

                Merge attrgraph branch into trunk

                --HG--
                extra : convert_revision : svn%3A3ed01bd8-26fb-0310-9e4c-ca1a4053419f/networkx/trunk%401364

            commit ad25ae40af532158bf1d6765d0dc822d67bcbcb3
            Author: aric <none@none>
            Date:   Mon Nov 3 04:37:22 2008 +0000

                Merged revisions 741-766,769-770,794-797,799,804-829,845-848,858-885 via svnmerge from
                https://networkx.lanl.gov/svn/networkx/branches/pre99

                ........
                  r741 | aric | 2008-02-18 18:29:21 -0700 (Mon, 18 Feb 2008) | 3 lines

                  pre99 branch refactoring directory layout
                ........
                  r742 | aric | 2008-02-18 18:30:17 -0700 (Mon, 18 Feb 2008) | 2 lines

                  pre99: missing utils.py
                ........
                  r743 | aric | 2008-02-18 20:42:25 -0700 (Mon, 18 Feb 2008) | 7 lines

                  pre99: graph,digraph,multigraph,multidigraph

                         list functions in __init__

                          remove xgraph,xdigraph
                ........
                  r744 | aric | 2008-02-18 20:42:58 -0700 (Mon, 18 Feb 2008) | 3 lines

                  pre99: example of labeled graphs
                ........
                  r745 | aric | 2008-02-18 20:44:46 -0700 (Mon, 18 Feb 2008) | 5 lines

                  pre99: tests for graph,digraph,multigraph,multidigraph

                         uses nose - run with nosetests
                ........
                  r746 | aric | 2008-02-18 20:45:23 -0700 (Mon, 18 Feb 2008) | 2 lines

                  pre99: __init__ for classes
                ........
                  r747 | aric | 2008-02-18 20:47:51 -0700 (Mon, 18 Feb 2008) | 2 lines
     - the "fixme" does not show up in the commit messages but `git log -S` looks also into the changes. so if you look at the individual commits (e.g. `git show 870ca9b9298f923235`), then a "fixme" got added or removed
        
    --> slight different issue here, it finds 'degree_correlation' but not the entire string: 'Logic error in degree_correlation', why is that?
        git log -S "Logic error in degree_correlation"
                    commit 4dff462e5259fff0ae39afb6f89ab0518afa980c
                    Author: dschult <none@none>
                    Date:   Wed Aug 3 03:25:34 2005 +0000

                        Update threshold to include degree_correlation(cs).

                        improve triangle_sequence, etc complexity by introducing
                        counters instead of repeatedly counting "d" symbols.

                        Also put in   enumerate(cs) in place of range(0,len(cs))
                        in a few places.

                        Added tests for degree_correlation(cs).

                        --HG--
                        extra : convert_revision : svn%3A3ed01bd8-26fb-0310-9e4c-ca1a4053419f/networkx/trunk%4036
    - Same explanation as question 2: `git log -S` not only looks at commit metadata but also the commit content (added lines and removed lines). `git show 4dff462` reveals that "Logic error in degree_correlation" got added.
    - It's a really powerful tool to be able to search all history, also for code that got removed and even if commit messages don't mention it.

4. git log -S "Logic error in degree_correlation" --patch --> should this theoretically do something similar to git annotate networkx/algorithms/threshold.py?
    - Somewhat: it would find commits that have adjusted that phrase, and show them.  It's a different format, maybe more appropriate in some cases.

---

5. What is the link for the GitHub so I can make an issue (as just mentioned)? I can't find it.
    -  https://github.com/cr-workshop-exercises/access-requests/issues/new/choose 


## Day 3

Materials: https://coderefinery.github.io/git-collaborative/

### Concepts

Materials: https://coderefinery.github.io/git-collaborative/concepts/

Your questions here: 

6. How do pushes to local fork compare to synchronizing to the upstream source where you forked from? Is there a way to commit and push to the place one forked from?
    - Very good question! We will demonstrate that later today and then also answer more here.
    - to already give a written answer: technically it is the same mechanism and you can push to either. often, one does not have write access to the original repo (if it is not yours) and can only push to your fork. but if you have write access to both, you can push to the original repository also.


### Collaborating within the same repository

Materials: https://coderefinery.github.io/git-collaborative/same-repository/

## Exercise session; back on stream at xx:00

Exercise preparation and materials: https://coderefinery.github.io/git-collaborative/same-repository/#exercise

Please remember to accept the e-mail and "unwatch".

What to do: Open an issue (assign to yourself), create new branch, make changes (create a new recipe file), push to the repository, open pull request, review someone elses 'PR' :heavy_check_mark:  (try to get until step 5)

How is it going? 
- Done: oooooo
- Not trying: o
- Don't know what to do (please ask for clarfication below): oo
- Major issues (please ask below): o
- I wish we had more time: ooo


Have fun :) 



7. I am participating as individual learner and joined on the recorded repo - I don't see the "Settings" tab. Is this only for those that open a team repo (e.g. the owner)? :+1: :+1: :+1: 
    - yes, only repository owners/admins can see settings tab on repositories
    - in this exercise we give you write access but not admin access, but for your own research group repositories you can choose to give all group members admin access
        - great, thanks for clarification!

8. Does GitHub recognize all the mentioned keywords for connecting the issues in both commit messages as well as pull request descriptions? It was only mentioned "fixes" under commit messages in the material, and then the rest of them (closes, resolves etc) under pull requests
    - yes, you can use them in commit messages and/or pull requets: close/closes/fix/fixes/resolve/resolves (maybe more?, same on GitLab)
      - Full list of words seems to be [here](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue)
    - sometimes I forget to add it to the commit messages but then I get another chance in the pull request to not forget. and if I forget then, I go to the issue and before closing it, I write down there which pull request or commit fixed it so that future generations understand what happened there and until when the issue was in the wild.

9. I made an issue to the centralized-workflow-exercise repo, but seem to not be able to assign the issue to myself -- i.e. when I open the issue, I can't click on `Assignees` . 
    - We will show this on stream, can you see the assignees tab?
    - it could be a permission issue, but write access should be enough to self-assign an issue (if I can trust the internet)

10. I guess that what is intended in point 5 is for us to make a pull request onto the original template? When I open pull request in my copy of the template I cannot see the option to make that the base, only my main appears. Sorry, I forgot to say that I am participating individually. 
    - PRs are used with *forks* (edit: or within the same repository), not with repositories generated by a template. *forks* keep a relationship with the original project, so GitHub has enough metadata to keep a relationship. Generating from a template instead is a completely different idea, where you want to start a completely new project but just copy the structure from an existing one, that is used as a template
        - but in this case we work within the same repository, not from a fork
        - but indeed please check whether you are pushing the branch to the correct repository. if the repository contains the word "template", then it is not the right one. it should be in this case either https://github.com/cr-workshop-exercises/centralized-workflow-exercise-recorded or https://github.com/cr-workshop-exercises/centralized-workflow-exercise
        - Sorry, I am confused. I am participating individually, I copied a template, created an issue, created a branch, added a file solving the issue, commited it, then merged the branch (points 1-4). Now I wish to do point 5, what am I supposed to do?
          - I think you might have followed the tab "part of a team or exercise room" instead of the tab "following on your own".
        - Ooops! You are right, sorry
          - you should still be able to create a new branch and open a pull request even if you are the only user in your repository (it seems strange but it is so). 
        - 

11. working in VScode in the git bash terminal, when I want to create a new file (here - in the current working directory), what would be a quicker way than doing it in the VScode GUi (click file - new file - choose file name - navigate to directory)?
    - When you are with the mouse in the explorer (the uppermost tab on the left with the two sheets), there appears a sheet with a little plus symbol in the upper right of that explorer which lets you create a new file in the current directory, can you see that? (not sure if it looks the same on all platforms)
        - yes, I see that, but I wondered more about a command line way from the git bash terminal?
        - you can also do `nano mains/filename.md`
        - Ah ok sorry, I am not sure if there is a command that opens it right away in the GUI to edit, but you can create a new file in the current working directory for example with `touch filename.xx` 
            - ah, great, thanks, I did not know about `touch`!
            - Uh, I just learned by trying: typing `code filename.xx` in the integrated terminal opens the new file in current location for editing. Does that work for you too? (`code` is also the command to start VSCode from command line)
                - yes, that works for me too! I first created the file using `touch` and then opened it using `code`

12. Can you provide us the terminal command for making a pull request on the repository? By now I've cloned the repository locally and made some commits.
    - it is possible to do this from command line but you would need an additional tool. the "normal" command line approach would be to first push the branch to the repository on github, and then create the pull request on the web.

13. When I am in VScode git bash terminal and cd to the directory of my choice and clone a repo in there - the rest of VScode seems to not know that I want to work there. I would expect the explorer and source control windows to navigate to the same directory on the fly. Is there a setting I have to set?
    - Good question, same behaviour here. Will check a bit and get back.

14. How do I do a pull request in command line? Here: https://coderefinery.github.io/git-intro/merging/, it says that this will be covered in the "collaborative git lesson" but i cant find it.
    - see question 12 (in short: typically on the web after pushing the branch to the github repo)

15. Once I do a pull request and I recieved a comment requesting to fix something else of the code, should I fix it using another pull-request or I should keep working on my branch and do a new commit?
    - In general, if it fits with the fixes of your original PR, you can add it to the same branch, then you have the discussion and fixes together. If not, you can also do a new branch and then a new PR.:+1:

> Add your questions below :) 

## BREAK until xx:10


16. After I cloned the repo, I forgot to make a new branch. I did changes in the local main branch and committed locally. What is the best way now to change it?
    - When making an accidental commit locally but *before pushing to remote*, it is luckily quite straightforward to recover / undo. You can try this `git reset HEAD~1` and then check `git status` what is the state of the repo.
    - It went back to the status before I committed. "nothing added to commit but untracked files present"
        - Ok that sounds good. You should now be able to create the new branch and continue normally.
    - could you also rename the branch and then push it? Is it possible to rename "main"?
        - yes, you can rename "main". Pushing also worked, you can look into branch "main_modified".  
        
17. I am in VScode git bash terminal: I have edited a new file  in a new branch. When want to stage it with `git add -p filename.md` it says "No changes." and then I cant commit because there is nothing staged. Why?
    - Have you rememebered to save the file?
        - yes
        - ![](https://notes.coderefinery.org/uploads/8a76b53a-3296-4b30-bb9c-4d5d6e3d3c0c.png)
            - Can you do `git status`?
                - yes, output is `On branch strawberry-salad
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        strawberry-salad.md

nothing added to commit but untracked files present (use "git add" to track)`
                    - Peculiar :) 
                        - ah, I tried without the -p option. now I think it worked? strange
                            - It seems the -p option is for interactive mode, I'm not sure what happened there.
                                - yeah I got it from the git cheatsheet https://aaltoscicomp.github.io/cheatsheets/git-the-way-you-need-it-cheatsheet.pdf
                                    - I see it - maybe it's easier not to use it for now :)
                                    - If it is the very first commit of the file, I think `-p` wouldn't work
                                    
18. Where can I place the "fixes #Y"? Title of pull request? Comment in pull request? Commit body/title?
    - You can try it out, where it links. I usually put it in the commit title, but when I forget I put it in the body/description of the PR

19. What does "a new branch with some half-finished work" mean? That there is something done there that is not committed in git?
    - I think it probably means: you've started working, and made the commits.  But it's not done enough to merge (maybe it still breaks other things?).  Commiting is fine, and you can even push so others can monitor the progress and provide help.  But you dont' want to merge until it's ready.

20. In relation to question 12 and 14. the previous days it was said that today we will learn how to push and pull from local repository to github. Maybe I missed something :) But could you teach us how to pull and push form local repository in command line? :+1:
    - Sorry I missed where did you show the command lines, could you paste the link?
        - Link 1: On the exercise here https://coderefinery.github.io/git-intro/sharing/ click on "terminal" and you see the workflow to push local to remote (=github).
        - Link 2: Today we pushed from local to collaborative repository: https://coderefinery.github.io/git-collaborative/same-repository/
            - Thank you! I've just managed to do a push. I suppose the pull that is similar


21. After that I wrote `git push origin new-branch-name`, I got `ERROR: Permission to cr-workshop-exercises/recipe-book.git denied to xxx, "`. Does it mean that I don't have write access?
    - I also had this error. After opening an issue in GitHub everything worked.
      - I am not sure why you saw this error and it is surprising to me that opening issue resolved it. Maybe something took a bit time? maybe temporary problem github-side?
      - Did this resolve or are you still having this issue? :+1:
          - I pushed to a wrong repository... (`cr-workshop-exercises/recipe-book`) :sweat_smile:

22. I opened an issue 'Pizza' and when I did the pull request I got a message 'changes requested'. Should I just edit the file? How do I submit the pull request again? And, the message contains: 'your pull request is not automatically linked in the issue, due to not explicitly including the "fixes #15"' - where should I add that? 
    - You could edit the description of the PR or add a comment to include the "fixes ..." 
    - For the requested changes, you can edit the file directly in the webinterface or also do it locally on your branch and push it again, the PR will then update with your commit.


23. When I push, I got this error message: fatal: unable to access 'https://github.com/cr-workshop-exercises/centralized-workflow-exercise.git/': The requested URL returned error: 403
    - Now it works.
        - Did you need to do anything? Or was it resolved by waiting a bit?
        - I didn't do anything, just waited and tried again.
            - Ok, some of the processed in background might take a moment. 
               - there might have been a temporary problem on github-side.

24. How are the pull request and issue are connected? Is it with the "#[number]" identifier?
    - Yes, if you mention just ""#number" in the PR, there will be a mention of this connection in the issue; if you mention it with one of the keywords, e.g. "fixes #number" it will also close the issue after the PR is merged

25. I see in the pull request shown now the issue was linked in the pull request title and not description as mentioned earlier - but this is probably equivalent and works also?
    - I believe both work, you could try what happens :)
        - It seems it might not work in title, based on Q #28, but I can try it later 

26. I accidentally merged the main branch to mine. How can I reverse the changes? I am using VS Code.
    - If you are working locally and have not pushed to remote after the merge, you can undo the merge with `git reset --hard HEAD~1` and then check `git status`.
    - But in general this isn't the worst thing to happen: sometimes people do this because they need updates.  It won't affect merging your branch→main later, git can figure it out.
        
27. Where on GitHub is issue #26 that is referenced in the instructor's pull request? I can find issue #16 but not #26
    - Could it be on the recorded repo instead of the non-recorded one?
    - I guess #26 refers to the pull request and #16 is the issue. You can see in the title the font color of #26 is different from the font color of #16 when you open the pull request
    - yes I think that was it.  In the "pull request" tab instead: https://github.com/cr-workshop-exercises/centralized-workflow-exercise-recorded/pull/26
        - Oh okay, that makes sense.

28. I don't think issue #16 is fully linked to that pull request? I don't see the "linked pull request" in the issue overview
    - Ah, I see it is referenced in the commit, not in the pull request itself.  You can see a commit listed under here:
    - https://github.com/cr-workshop-exercises/centralized-workflow-exercise-recorded/issues/16
        - The commit is added to both, so it is possible to click to the issue, but the full integration of the pull request into the issue does not seem to be there. Probably the keyword+number needs to be in the pull request description?

> [off-topic comment removed]
- Radovan: this is outside the scope of this workshop

### Code review

Materials: https://coderefinery.github.io/git-collaborative/code-review/


29. When opening a file inside a repository, is it by default a .md file? I would like to use this version control with Word documents, is it possible to upload a word document and work collaboratively with my collegues on the Github web? I assume working on code is possible, by uploading Rscripts or .md files, right?
    - it can be any kind of file, some functionality (e.g. looking at changes may be a bit weird for some file types), you define the type by adding the extension (eg. `.txt`, `.md`, `.py` , etc.)
    - works best with text files, rather than binary file formats (like .doc); it seems there is ways to work with word files too though (https://olickel.com/tracking-word-documents-with-git) but no experience
    Great, tanks!

30. How do I conveniently reference a commit in a conversation? If I click 'copy', to the right of the commit title, it copies the whole hash.
    - Hm.  I might select the short form manually and Control-C.  I haven't often had this problem, somehow, but it does seem familiar.
    - Thanks for the clarification on-stream. For context: in comments to my PR, someone suggested a change to a file that I had added, and I happened to commit a change to that effect almost at the same time, so wanted to reference the commit that implemented the requested change.

31. After the course ends, will there be some type of Slack channel or chat forum if we run into errors in the future (that is associated with CodeRefinery):+1:
    - You can join our chat: https://coderefinery.zulipchat.com (sorry, trying to do too many things at once :sweat_smile: ), there we have a `#help` channel which can be used to ask questions and we have many people excited to help :) The chat is however not specific for the course.
    - How often is it monitored, the chat forum?
        - We hang out there all the time, but depending how busy people are it can take a day or two to get an answer (also depends on the complexity of the question)
    - We also provide two "bring your own code" sessions after the workshop, where you can can drop in and ask questions (see bottom of schedule: https://coderefinery.github.io/2024-09-10-workshop/#schedule); :+1:
    
> Thank you for clarifying the difference between pull and pull request, that a pull request means asking the owner to make a pull.:+1: :+1:

32. How to link a pull request to an issue? 
    - See question 8 for some keywords that you can use to link PR and issues.
    - For automatically closing the issue (and getting the clickable link), it is enough with keyword+nr in commit message (on the branch in the pull request). But for full link it seems keyword+nr needs to be in pull request description as well :+1:

## Lunch break, we resume at xx:00

You can ask more questions below, but please also remember to take a break :) 


33. I pressed delete branch on GitHub after the Pull Request was approved, then tried to get it updated locally as well by doing 'git pull', but my local branch was not deleted. I can still see it if I do 'git branch', and git pull says 'already up to date'. How to get local repo updated/in synch with remote, and remove that leftover branch from the pull request?
    - I believe you always have to delete the branch on both remote and locally. To delete the local branch you can use `git branch -d branchname` or do so manually in e.g. VSCode or your preferred environment. 
    - one thing that you can do is `git fetch --prune` and that will inform local repo which remote branches don't exist anymore and update the info about tracking. but as far as I know it won't delete local branches. for git, local branch and remote branch are two different pointers which can happen to point to the same commit at times.
      - side comment: not sure we talk about `git fetch` or `git fetch origin` but it is a way to fetch commits that don't exist locally without modifying local branches. this allows to look changes before merging them ("git pull" does two things: "git fetch" followed by "git merge") 

## Contributing changes to repositories that belong to others

Materials: https://coderefinery.github.io/git-collaborative/forking-workflow/

34. Why fork instead of cloning? Is it to get it into ones own GitHub account?
    - Basically yes.  You can always clone to work on your own computer, but to make it visible to the upstream (so that you can make a PR and they can merge it), it needs to be on GitHub.  Since you can't change their repo, you have to "fork (the github concept)"
        - Ah, so to work on a clone from for example google jax one would have to have one's credentials in that account? Which would basically be impossible I guess, and fork is the only way
        - That is right!

35. How can I move out of the repo I am in (VScode - git bash terminal) in order to move into another one? Other than opening a new window?
    - I think it's "open new project" or similar - yes, it's basically a new window.  These editors are "one window per project (=directory)"
        - ah, ok. thanks. So when I close a VScode window where I am in centralized-workflow-exercise-recorded I kind of "log off"?

36. What is the difference between pull request and issues? they both suggest changes to the current version of the project. What makes it different
    - Issue is basically free-form text.  Pull request is a structured code change from branch to branch which has a specific action: merging it.
    - I actually was going to ask the same thing. Can you explain your answer furhter? like the objective of each, free-form text v. not, and how they are related (or not).
    - Issue: You can inform about something to be improved, and discuss about it, but at this point there is no changes yet. 
    - PR: Now we have changes, someone maded a suggestion and this suggestion can be discussed in the PR and further adaptions can be made

37. When one writes 'git push', what is being done compared to for example 'git push -u origin branchname'?
    - `git push` alone tries to find the defaults and work automatically
    - `git push origin branchname` explicitely says what to do (what remote, what branch)
    - `git push -u origin branchname` adds a `-u` which is "remember this as defaults for the future"
        - So if one is pushing a branchname that will be deleted in the future after merging, then one should not use the '-u' option? As this will then be used by 'git push' as default in the future when it is not in use anymore

38. How do I do step 3 with the cross-reference? I am at the commit portion where I can either commit to my new branch or commit and create a new branch and a pull request, but that's not exactly what I want either...
    - you can cross reference issue in your commit message, for eg: `fix #issuenumer` ` resolve #issue number` . If you don't want to cross reference with your commit message , you can do it in your pull request. Please check some of the pull request we had done today where we cross referenced the issue. I hope this answers your question

39. In the pull request, how do you refer to the issue, like #25 abcdefg?
    - Entering `#25` should make a link to it, I think.  Writing `fixes #25` should link it so that merging the pull request will close that issue.

40. Atm, there is only one closed pull request for the forking-workflow-exercise repo.
    - THanks for letting us know.

41. What is the automated test? Like why did it fail in the example? Does it mean that it is not meeting certain criteria that was manually made?
    - Basically yes, the automatic test can check any criteria we want.  In this case it makes sure it has an "ingredients" and "instructions" section - simple text check (it's in check_recipes.py)
    - Do a lot of people use this feature? b/c I assume you need to make a reference script/text for the test to check

42. Why do you need the -u after git push origin? What does it do?
    - the long version of -u is --set-upstream, it adds a tracking reference to the upstream server you are pushing to

43. Why does 'compare changes' not work automatically when I ask it to show them before syncing the fork?
    - When I compare upstream main with my branch on my fork (not the main branch my fork), I can see the changes and assosiated commits and pull request. But default main comparison doesn't show any changes. Good to chaeck stack flow discussion [here](https://stackoverflow.com/questions/74943541/after-a-github-fork-how-can-i-compare-my-branch-to-a-branch-in-the-upstream-rep).

44. What is a clear use case for why I would fork v. clone?
   - Fork: Creates a personal copy of someone else’s repository on your GitHub account. Used for contributing to projects you don’t have write access to. You can make changes to your forked repository and then propose those changes to the original repository via a pull request. This allows the maintainers of the original repository to review and potentially merge your changes.
   - Clone: Cloning creates a local copy of a repository on your machine. This is useful for working offline, performing tests, or making personal changes. You can work on the cloned repository independently, and if you have write access, you can push your changes back to the remote repository.
   - You can clone from a forked repository, but in order to contribute to someone's repository where you don't have write access, you must fork it first

45. How long has CodeRefinery been around doing these workshops? Who started it?
  - You can find out about the history on our website: https://coderefinery.org/about/history/
  - We have been doing these workshops since 2016, first in person, then in Zoom, and most recently streamed.

## Exercise session; we will resume at xx:45

Exercise materials: https://coderefinery.github.io/git-collaborative/forking-workflow/#exercise

See also help topics below the exercise box

How is it going? 
- Done: oooooooo
- Not trying: oo
- Don't know what to do (please ask for clarfication below): o
- Major issues (please ask below): o
- I wish we had more time: o

Good luck and have fun :) 


> Tip: It just happened to me that I misspelled the branch using `git switch --create misspllessed-banrch`. You can rename the branch with `git branch -m correctly-spelled-branch`

46. Shoot, I only did git clone from the original repo, not fork before. Now I cannot push I think? How can I clean this up?
    - One way is to adjust the remote's URL.  `git remote set-url origin THE_RIGHT_URL` - 
        - but then I first have to fork on github, no? and then link to "my fork"?
        - Oh yes.  You still need to fork first, but then this method can adjust your local copy to point to your fork, then you can push.  You usually can fix things, if you want
    - (you can also always save the change, delete and re-clone and re-apply the change.  More crude but doesn't require remembering anything.)
        - great, worked, thanks!

47. I think i created a pull request directly from command-line by "git push origin lasagna" ("lasagna" is the name of my arbitrary branch). I forked the original repository, than cloned the fork to my computer, worked on it locally and pushed up. Does this mean I don't need to merge it with my own fork first? Is "origin" means upstream in this case?
    - "origin" is wherever you first cloned from: so in this case "origin" is your own fork.  I think you have made a branch on your fork (which is exactly what you want!). - you are now probably ready to make the pull request.

48. could you explain why I have o set my forked repo as upstream before I can push? ```$ git push
fatal: The current branch strawberry-salad has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin strawberry-salad

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'. ``` 
    - Hmm, this is about linking the branches, so git does not know yet which remote branch you would like to push your local branch to. You could do `git push origin strawberry-salad` to specify directly. 
    - okay, thanks. so is this a combination of merge and push then?
        - `git push origin strawberry-salad` will upload all commits that are referenced locally by `strawberry-salad` to origin and then update the branch `strawberry-salad` also on origin. It will only do that if the remote branch does not contain other commits (it will not let you accidentally overwrite commits). A merge commit is then not needed since it only moves `strawberry-salad` forward on origin. Hopefully that clarified it but please ask more if not.
    - You can `git push origin strawberry-salad` and it knows where to go.  See this qusetion 37 for an answer about what the`-u` means. Basically, `-u` once sets the default, so than it the future you don't have to specify the `origin` or the branchname in the future.

49. Sorry, I missed how to link a pull request to an issue, could you please say again how to do this? I tried putting the issue number #n in the title, but it did not work
    - It seems that the linking needs to happen in the description (or a comment) of the pull request, rather than the title.
        - Thanks. I tried adding "Issue #n" to the comments, but still not there. There may be some fixed format to do it
            - You need to write `Fixes #n`, or `fixes #n`, `Closes #n` (or one of the other keywords)
                - Thanks, I guess that the list is in https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/using-keywords-in-issues-and-pull-requests
                - What about if it only solves part of an issue? What would be the preferred option to use?
                    - I have seen "related #number" (or just the #number without anything before), then the PR is mentioned in the issue automatically but not closed. But this may also relate to writing good issues, maybe that issue should rather be two issues? 
                        - Got it, thanks.

50. Is there a way to sync changes at upstream fork source (ie after merge) down to forked repo via CLI?
    - this is how I would do it using the command line: "git pull UPSTREAM-URL BRANCHNAME", followed by "git push FORK-URL BRANCHNAME"
        - Is the BRANCHNAME in the pull command the source (remote fork source) or target (local repo)?
            - good question. indeed it is the source. `git pull URL BRANCHNAME` will modify my current branch name. To avoid any confusion I use the same branch name locally and before running the `git pull` command I make sure I am on the local branch. `git pull` modifies the current branch.
                - Thanks. The URL, does it need to be https (and not ssh)?
                - Depends on if you have ssh or https set up.  I'd recommend using whatever you have been using (you can check with `git remote -v`).
                    - I tried now and both ssh and https worked for pulling from fork source used in the exercise, but I guess for more private repos (like the google ones), one would probably have to use https to pull from fork source to local repo?
                     

51. Is it that writing `#25` will make a link to that issue/PR number, but only `fixes #25` and similar makes it where it gets closed.  Does this show up differently on the pages?
    - yes, if you use `#25` in a commit or pull request and an issue or pull request with the number 25 exists, it will cross-reference them. only the special keywords are interpreted to also close issues once they are merged to the default branch.

52. If one forgets to create a new branch and sends the pull request, should one try to fix the name ("main) or just leave as is? (I tried to fix and made a mess :-)  )
    - You could wait until it is merged and then re-create the fork if this is a one-time thing. I would only clean up (rewind main and put the change on a branch) if I am actively working on the fork on other things as well.
    - Sending a PR from main really only starts to become a problem for the next PR few months later. When you open it, you then see that there is a large number of commits in there which you did not intend to send. When you see this, then this is the reason. But it can always be repaired and don't hesitate to contact us on CodeRefinery chat to help repairing :-)

53. Can the instructors merge some pull requests, so that we can try synching back to the fork? Ah nevermind, I just needed to refresh GitHub, now there are some commits/merges
    - Could this be done on the non-recorded repository also?
         - Thanks for reminder. going there to help merge.
             - Thanks! :+1:

54. My issue is resolved (#4) and the pull request accepted, but I cant find my recipe?
    - is this in the recorded one or the unrecorded? 
        - recorded
          - ok looking ... just a sec ... 
              - nevermind, it is just not in the folder that I expected it in. my bad!
                  - yes. no problem. the file could be git moved to the right folder as follow-up. nice that we solved it.
                      - is there a way to do it on github? or do I have to correct it in my clone of my fork and then push it again?
                          - I admit I don't know how to do it on GitHub. I would have cloned/pulled, fixed it locally, then pushed back. Maybe someone knows how to do that?

55. How to delete the merged branch in the forked repo in GitHub? 
     - go back to the pull request (which is now closed?) and in there you can delete it. or in your fork go to branch overview (it's next the button which says which branch you are on).
         - Thanks, found the delete button now in the bottom of pull request

> Questions can continue below the Feedback (so that we will see that there is new ones ), but please take a moment to let us know how today was going for you

## Feedback Day 3

### News from day 3

- Today we covered how to contribute to repositories that we are a member of as well as repositories that we were not a member of 
- This concludes  the introduction and collaborative version control lessons and exercises
- Next week we will step away from version control and get to know different tools and techniques that can help you write FAIR code and software such as documentation, licensing, Jupyter, modular code development, automated testing
- There will be demos instead of exercise sessions, but you can do the exercises after the workshop days and use the notes to ask questions, or join our chat: https://coderefinery.zulipchat.com or the "bring your own code sessions" in october; see [schedule](https://coderefinery.github.io/2024-09-10-workshop/#schedule)
> More info on the CodeRefinery ambassador program : https://coderefinery.org/join/individuals/#coderefinery-ambassador

Today was (vote for all that apply):
- too fast:
- too slow:👍🏿
- right speed:oooooooooooooooo
- too advanced:
- too basic: 
- right level: ooooo
- needed more exercise time:ooooo
- needed less exercise time: oooo
- I will use what I learned today: oooooooooooooooooo
- I would recommend today to others: oooooooooooo
- I would not recommend today to others:

One good thing about today:
- I learned to work in an collabrative environment:+1: :+1: :+1: :+1:
- Github has a lot of tools and resources for collaboration. :+1:
- Understood why, in some cases, it's useful to fork a project instead of just cloning the original one
- I understood a lot more git commands than just commit, push and pull, was finally able to connect github with VScode and git bash (command line)
- Behind the scenes team were fast to answer  questions and solving issues :+1::+1: 
- Thank you for providing help for both GitHub interface as well as git CLI
- I confidently and corectly used things learned yesterday.

One thing to improve for next time: 
- We want cats! :+1: 
- More answering of questions from notes on stream (answering by the lecturers)

Any other feedback?
- Is there any chance on a lecture on CI/CD?
    - Yes, day 6 (next thursday)
        - what is CI/CD? :+1:
        - It stands for Continuous integration and delivery, take a peek: https://coderefinery.github.io/testing/continuous-integration/
- See you next week!
- This was a fantastic week 1, thank you for it. I am glad I used time I do not have to attend it. :-)
- Thank you for making all this effort to create this interactive course :heart:. It is also great how you set up the course with the stream, the editing document, the different windows, the people in the background supporting the presenters, answering questions in real time and so on. This is really professional. It is a bit confusing to keep up with everything as a beginner, but since it is possible to go through the material again, I am sure it will get easier and more plausible.

Questions can continue:

- 56. Is it possible for us to go through the collaborative exercises at home alone until next week and still keep the access to the recorded repository in order to learn?
    - Yes. Best to join the chat and let us know if you need someone to do something from our side: https://coderefinery.zulipchat.com :+1:
    - Awesome thank you! :+1:
