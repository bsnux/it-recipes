Git: Replacing master branch entirely with another branch
==========================================================

It's not a good practice, but it could be useful to replace entirely a master with
a different branch. You only need to execute following commands:

	git checkout mybranch
	git merge -s ours master
	git checkout master
	git merge mybranch

Basically, we used **ours** as recursive strategy.