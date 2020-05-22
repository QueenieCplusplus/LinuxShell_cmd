# LinuxShell_cmd
all basic

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

          ✗ cd desktop
          ➜  desktop gcc 522.c
          ➜  desktop ./a.out
          this is vivy's shell and C.%  





