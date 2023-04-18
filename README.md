# ROOTonWindows11
How to fix  error: Unable to init server: Broadway display type not supported: localhost:0 Error: cannot open display: localhost:0  
For CERN - ROOT on Win11. 
Assuming that ROOT v6-24-00, Ubuntu 18.04 and xming are already installed.

1. right click on the xming app and click on "view log"
2. scroll all the way down to "... rejected IP xxx.xx.xx.xx" and copy the IP address
3. Run Notepad as administrator
4. On notepad: file -> open -> Loacl disk (C:) -> Program files (x86) -> xming -> X0.hosts
5. Delete the IP adress in that file and paste the one you copied from xming's log and close notepad
6. close the terminal (ubuntu) and exit xming (basically exit from everything 
7. run xming THEN ubuntu
8. (make sure ROOT is working properly)
9. copy and paste this line in terminal:
    `export DISPLAY="`sed -n 's/nameserver //p' /etc/resolv.conf`:0"`
10. test it works now by simply typing 
    `firefox` 
    in terminal
