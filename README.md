# LinuxShell_cmd
all basic

指令執行順序： 內建指令 > 別名 > 環境變數 $PATH 的定義。

# Cmd 指令列

* ;

一行指令列執行多指令。

* && 

如前者指令正確執行完畢後，方才執行後者。

* ||

若前者指令執行完畢且錯誤，方才執行後者。

# Env Path 執行路徑與環境變數

* echo $path

環境變數，讓我們全域呼叫其變數名稱，便能找到指定的路徑值，如 呼叫 ps, 其實就是執行 /bin/ps 此檔案。

另外，倘若該路徑下有著與系統指令同名的執行檔案，也可能執行到不同檔案，故針對同路徑下的檔案命名方式要極為注意喔～

安全考量上，存在駭客藉由與系統指令同名檔案讓管理者不小心執行該檔案！（借刀殺人之法。）


          ✗ echo $path
         /usr/local/opt/python@3.8/bin 
         /usr/local/opt/python@3.8/bin 
         /Users/pintred/perl5/bin 
         /Library/Frameworks/Python.framework/Versions/3.8/bin 
         /usr/local/bin 
         /usr/bin 
         /bin 
         /usr/sbin 
         /sbin 
         /Applications/VMware Fusion.app/Contents/Public 
         /usr/local/go/bin
         # 其實以上應用程式會在 Linux 系統以 : 分隔彼此。 Sperate with each other by colon.
         
# Execution 執行

tips

     ./ <file_name>


example:

https://github.com/QueenieCplusplus/LinuxShell_cmd/blob/master/522.c

          ✗ cd desktop
          ➜  desktop gcc 522.c
          ➜  desktop ./a.out
          this is vivy's shell and C.%  
          
![image](https://scontent.ftpe8-1.fna.fbcdn.net/v/t1.0-9/99371844_121571682880808_1724959029005910016_o.png?_nc_cat=109&_nc_sid=730e14&_nc_ohc=RxP27GpnHDAAX8_NjqY&_nc_ht=scontent.ftpe8-1.fna&oh=53a71373b049ce83bf0c236cff26059f&oe=5EED12F2)

# Alias 別名

 * alias
 
 設定別名方式
 
     alias ccc='cal'
     
           ✗ ccc
                5月 2020         
          日 一 二 三 四 五 六  
                          1  2  
           3  4  5  6  7  8  9  
          10 11 12 13 14 15 16  
          17 18 19 20 21 22 23  
          24 25 26 27 28 29 30  
          31
 
 查看別名
 
                    ✗ alias
                    -='cd -'
                    ...=../..
                    ....=../../..
                    .....=../../../..
                    ......=../../../../..
                    1='cd -'
                    2='cd -2'
                    3='cd -3'
                    4='cd -4'
                    5='cd -5'
                    6='cd -6'
                    7='cd -7'
                    8='cd -8'
                    9='cd -9'
                    _='sudo '
                    afind='ack -il'
                    egrep='egrep --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn,.idea,.tox}'
                    fgrep='fgrep --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn,.idea,.tox}'
                    g=git
                    ga='git add'
                    gaa='git add --all'
                    gap='git apply'
                    gapa='git add --patch'
                    gau='git add --update'
                    gav='git add --verbose'
                    gb='git branch'
                    gbD='git branch -D'
                    gba='git branch -a'
                    gbd='git branch -d'
                    gbda='git branch --no-color --merged | command grep -vE "^(\+|\*|\s*(master|develop|dev)\s*$)" | command xargs -n 1 git branch -d'
                    gbl='git blame -b -w'
                    gbnm='git branch --no-merged'
                    gbr='git branch --remote'
                    gbs='git bisect'
                    gbsb='git bisect bad'
                    gbsg='git bisect good'
                    gbsr='git bisect reset'
                    gbss='git bisect start'
                    gc='git commit -v'
                    'gc!'='git commit -v --amend'
                    gca='git commit -v -a'
                    'gca!'='git commit -v -a --amend'
                    gcam='git commit -a -m'
                    'gcan!'='git commit -v -a --no-edit --amend'
                    'gcans!'='git commit -v -a -s --no-edit --amend'
                    gcb='git checkout -b'
                    gcd='git checkout develop'
                    gcf='git config --list'
                    gcl='git clone --recurse-submodules'
                    gclean='git clean -id'
                    gcm='git checkout master'
                    gcmsg='git commit -m'
                    'gcn!'='git commit -v --no-edit --amend'
                    gco='git checkout'
                    gcount='git shortlog -sn'
                    gcp='git cherry-pick'
                    gcpa='git cherry-pick --abort'
                    gcpc='git cherry-pick --continue'
                    gcs='git commit -S'
                    gcsm='git commit -s -m'
                    gd='git diff'
                    gdca='git diff --cached'
                    gdct='git describe --tags $(git rev-list --tags --max-count=1)'
                    gdcw='git diff --cached --word-diff'
                    gds='git diff --staged'
                    gdt='git diff-tree --no-commit-id --name-only -r'
                    gdw='git diff --word-diff'
                    gf='git fetch'
                    gfa='git fetch --all --prune'
                    gfg='git ls-files | grep'
                    gfo='git fetch origin'
                    gg='git gui citool'
                    gga='git gui citool --amend'
                    ggpull='git pull origin "$(git_current_branch)"'
                    ggpur=ggu
                    ggpush='git push origin "$(git_current_branch)"'
                    ggsup='git branch --set-upstream-to=origin/$(git_current_branch)'
                    ghh='git help'
                    gignore='git update-index --assume-unchanged'
                    gignored='git ls-files -v | grep "^[[:lower:]]"'
                    git-svn-dcommit-push='git svn dcommit && git push github master:svntrunk'
                    gk='\gitk --all --branches'
                    gke='\gitk --all $(git log -g --pretty=%h)'
                    gl='git pull'
                    glg='git log --stat'
                    glgg='git log --graph'
                    glgga='git log --graph --decorate --all'
                    glgm='git log --graph --max-count=10'
                    glgp='git log --stat -p'
                    glo='git log --oneline --decorate'
                    globurl='noglob urlglobber '
                    glod='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ad) %C(bold blue)<%an>%Creset'\'
                    glods='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ad) %C(bold blue)<%an>%Creset'\'' --date=short'
                    glog='git log --oneline --decorate --graph'
                    gloga='git log --oneline --decorate --graph --all'
                    glol='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset'\'
                    glola='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset'\'' --all'
                    glols='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset'\'' --stat'
                    glp=_git_log_prettily
                    glum='git pull upstream master'
                    gm='git merge'
                    gma='git merge --abort'
                    gmom='git merge origin/master'
                    gmt='git mergetool --no-prompt'
                    gmtvim='git mergetool --no-prompt --tool=vimdiff'
                    gmum='git merge upstream/master'
                    gp='git push'
                    gpd='git push --dry-run'
                    gpf='git push --force-with-lease'
                    'gpf!'='git push --force'
                    gpoat='git push origin --all && git push origin --tags'
                    gpristine='git reset --hard && git clean -dffx'
                    gpsup='git push --set-upstream origin $(git_current_branch)'
                    gpu='git push upstream'
                    gpv='git push -v'
                    gr='git remote'
                    gra='git remote add'
                    grb='git rebase'
                    grba='git rebase --abort'
                    grbc='git rebase --continue'
                    grbd='git rebase develop'
                    grbi='git rebase -i'
                    grbm='git rebase master'
                    grbs='git rebase --skip'
                    grep='grep --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn,.idea,.tox}'
                    grev='git revert'
                    grh='git reset'
                    grhh='git reset --hard'
                    grm='git rm'
                    grmc='git rm --cached'
                    grmv='git remote rename'
                    groh='git reset origin/$(git_current_branch) --hard'
                    grrm='git remote remove'
                    grs='git restore'
                    grset='git remote set-url'
                    grss='git restore --source'
                    grt='cd "$(git rev-parse --show-toplevel || echo .)"'
                    gru='git reset --'
                    grup='git remote update'
                    grv='git remote -v'
                    gsb='git status -sb'
                    gsd='git svn dcommit'
                    gsh='git show'
                    gsi='git submodule init'
                    gsps='git show --pretty=short --show-signature'
                    gsr='git svn rebase'
                    gss='git status -s'
                    gst='git status'
                    gsta='git stash push'
                    gstaa='git stash apply'
                    gstall='git stash --all'
                    gstc='git stash clear'
                    gstd='git stash drop'
                    gstl='git stash list'
                    gstp='git stash pop'
                    gsts='git stash show --text'
                    gstu='git stash --include-untracked'
                    gsu='git submodule update'
                    gsw='git switch'
                    gswc='git switch -c'
                    gtl='gtl(){ git tag --sort=-v:refname -n -l "${1}*" }; noglob gtl'
                    gts='git tag -s'
                    gtv='git tag | sort -V'
                    gunignore='git update-index --no-assume-unchanged'
                    gunwip='git log -n 1 | grep -q -c "\-\-wip\-\-" && git reset HEAD~1'
                    gup='git pull --rebase'
                    gupa='git pull --rebase --autostash'
                    gupav='git pull --rebase --autostash -v'
                    gupv='git pull --rebase -v'
                    gwch='git whatchanged -p --abbrev-commit --pretty=medium'
                    gwip='git add -A; git rm $(git ls-files --deleted) 2> /dev/null; git commit --no-verify --no-gpg-sign -m "--wip-- [skip ci]"'
                    history=omz_history
                    l='ls -lah'
                    la='ls -lAh'
                    ll='ls -lh'
                    ls='ls -G'
                    lsa='ls -lah'
                    md='mkdir -p'
                    rd=rmdir
                    run-help=man
                    which-command=whence


