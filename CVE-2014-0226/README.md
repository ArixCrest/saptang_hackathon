# CVE-2014-0226
## Bug Overview
Race condition in the mod_status module in the Apache HTTP Server before 2.4.10 allows remote attackers to cause a denial of service (heap-based buffer overflow), or possibly obtain sensitive credential information or execute arbitrary code, via a crafted request that triggers improper scoreboard handling within the status_handler function in modules/generators/mod_status.c and the lua_ap_scoreboard_worker function in modules/lua/lua_request.c.
## Aim
Write a working exploit for this CVE. <br>
Install vulnerable service in a VM/Docker and ensure to meet the condition so that you
can exploit it. <br>
Run your exploit on the vulnerable service and make a video of it.
Write a brief report about this bug including your exploit code and link for exploit and
Video proof.<br>
## Setting up the environment
In the CVE-2014-0226 directory run the following command to build the dockerfile
```
docker build -t <name of image> .
```
The docker file should now be build with the name that you gave.
To start a container use the following command
```
docker run --name <name of the container> -it <image ID>
```
This should land you in the interactive shell, where you can start the server using
```
./httpd
``` 
and then to run the exploit simply run
```
python3 cve_226.py
```

