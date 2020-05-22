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

https://github.com/QueenieCplusplus/POSIX/blob/master/README.md#script

tips

     ./ <file_name> // after chmod 755
     
     bash <file_name>
     
     source <file_name>
     
     . <file_name> // . + space + param
         

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
                    (略)
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

# Profile

不同作業系統的人機介面則會有不同的 start-up file。
像我是用蘋果電腦，且使用 Bash，則找到執行編輯檔案，其路徑為 ~/.bash_profile。

* .Profile

          #GOPATH
           export GOPATH=~/Applications/Go
           #GOROOT
           export GOROOT=~/Documents/go
           #PATH
           export PATH=$GOROOT/bin:$GOPATH/bin:$PATH
