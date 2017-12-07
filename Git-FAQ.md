# remove local untracked files

If you want to see which files will be deleted you can use the -n option before you run the actual command:
```bash
git clean -n
```

Then when you are comfortable (because it will delete the files for real!) use the -f option:
```
git clean -f
```

Here are some more options for you to delete directories, files, ignored and non-ignored files
To remove directories, run `git clean -f -d or git clean -fd`
To remove ignored files, run `git clean -f -X or git clean -fX`
To remove ignored and non-ignored files, run `git clean -f -x or git clean -fx`

# remove remote files but reserve the local ones

If you have some files which have been pushed to remote branch, now you need to delete them but keep them in local.

```bash
git rm --cached file1.txt
git commit -m "remove file1.txt"
```
And to push changes to remote repo
```bash
git push origin branch_name
```
