Discarding ALL changes 
If you have a lot of commited changes that are not yet pushed and you would like to make your branch identical to what's on the remove, you'll need to reset the branch locally and possibly pull as well.

In the case of the master branch:

```bash
git reset --hard origin/master
git pull origin master
```