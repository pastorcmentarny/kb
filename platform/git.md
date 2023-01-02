* ```alias caa = commit -a --amend -C HEAD``` Which will take all uncommitted and un-staged changes currently in the
  working directory and add them to the previous commit, amending it before pushing the change up.
* ```bclean = "!f() { git branch --merged ${1-master} | grep -v " ${1-master}$" | xargs -r git branch -d; }; f" ```
  Cleanup merged branches. The above will remove local branches that have already been merged to master by default, but
  you can pass a different one if you need to
* ```git rm -r --cached crap.file``` - remove file from git index
* ```git shortlog -sn --no-merges``` Show's highscore for who commit most :D
* Git Binary search, or bisection, is useful when troubleshooting
  git rm -r --cached .
  git add .
  git commit -m 'git cache cleared'
  git push
* 