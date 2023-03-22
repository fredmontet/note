Git
===

## Clean your repositoryi

	git clean -dfX

git-clean - Remove untracked files from the working tree
	-d for removing directories
	-f remove forcefully
	-n Don’t actually remove anything, just show what would be done.
	-X Remove only files ignored by Git. This may be useful to rebuild everything from scratch, but keep manually created files.	

If the ignored files are already added to the index/staging, you must remove the files from the tracking index before using the above clean command.

	git rm -rf --cached .

Then add the files except the ones mentioned in the .gitignore file

	git add .

Source : https://stackoverflow.com/questions/46273032/is-there-a-way-to-remove-all-ignored-files-from-a-local-git-working-tree


## Prendre des commits d'une autre branche

	git cherry-pick <commit>

## Diffing

	git diff <file-name>   # Check the diff in a file
	git diff --cached      # Check the diff when staging

## Changer l'URL d'une branche remote

	git remote -v	# Check the URL of the remote
	git remote set-url origin <new-url>	# Change the URL
	git remote -v	# Check the new URL

## Branching

	git remote -v 	# List the remote branches
	git branch -v 	# List the local branches
	git branch -u origin/dev dev 	# "Connect" the remote and local dev branches
	git push origin --delete <branch_name> # Delete a remote branch
	git branch -d <branch_name> # Delete a local branches

## Delete stale remote branches

	git branch -a	# to check all the branches
	git remote prune origin

## Tag

	git tag vX.Y
	git push origin vX.Y

	git tag -a "<tag_name>" -m "my message"   # Make an annotated tag with a message
	
e.g. git tag -a v1.4 -m "my version 1.4"

## Delete a Tag

	git tag -d vX.Y			# Delete locally
	git push --delete origin vX.Y	# Delete on remote	

## Ziper le code

	git init       # on the root of the project folder
	git add .      # note: android studio already created .gitignore
	git commit -m 'ready to zip sources'
	git archive HEAD --format=zip > /tmp/archive.zip

## Revenir au dernier commit, supprimer les modifications

	git reset --hard HEAD

## Effacer le dernier commit mais sans supprimer le code

	git reset --soft HEAD~1

## Changer le message du dernier commit

	git commit --amend

## Supprimer une branch

Local:

	git branch -d <branchName>

Remote:

	git push origin --delete <branchName>

Conseil:

Don't forget to do a git fetch --all --prune on other machines after deleting the remote branch on the server. ||| After deleting the local branch with git branch -d and deleting the remote branch with git push origin --delete other machines may still have "obsolete tracking branches" (to see them do git branch -a). To get rid of these do git fetch --all --prune

## Gary's deluxe merge

Il y a 2 branches, la test a des commits d'avances sur la master mais celle-ci a eu des commits par d'autres dev.

	git checkout master 
	git pull --rebase
	git checkout test
	git rebase -i master

Si conflit:

	git mergetool
	git rebase --continue

Une fois terminé:

	git checkout master
	git merge test
	git push origin master

## Scala repository hygiene manifesto

As git history is forever, we take great pride in the quality of the commits we merge into the repository. The title of your commit will be read hundreds (of thousands? :-)) of times, so it pays off to spend just a little bit more time to polish it, making it descriptive and concise. Please take a minute to read the advice most projects agree on, and stick to 72 or fewer characters for the first line, wrapping subsequent ones at 80 (at most).

When not sure how to formulate your commit message, imagine you're writing a bullet item for the next release notes, or describing what the commit does to the code base (use active verbs in the present tense). When your commit title is featured in the next release notes, it will be read by a lot of curious Scala users, looking for the latest improvements. Satisfy their thirst for information with as few words as possible! Also, a commit should convey clearly to your (future) fellow contributors what it does to the code base.

Writing the commit message is a great sanity check that the commit is of the right size. If it does too many things, the description will be unwieldy and tedious to write. Chop it up (git add -u --patch and git rebase are your friends) and simplify!

To pinpoint bugs, we often use git bisect, which is only effective when we can count on each commit building (and passing the test suite). Thus, the CI bot enforces this. Please rebase your development history into a sensible list of self-contained commits that tell the story of your bug fix or improvement. Carve them up so that the riskier bits can be reverted independently. Keep changes focussed by splitting out cleanups from refactorings from actual changes to the logic.

This facilitates reviewing: a commit that reformats code can be judged quickly not to affect anything, so we can focus on the meat of the PR. It also helps when merging between long-running branches, reducing conflicts (or providing at least a limited scope for each one).

Please do not @-mention anyone in the commit message -- that's what the PR description and comments are for. Every time a commit is shuffled through github (in a merge in some fork, say), every @-mention results in an email to that person (the core team treats them as personal email, straight to their inbox, so please don't flood us :-)).

## To read

https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History#Changing-Multiple-Commit-Messages
