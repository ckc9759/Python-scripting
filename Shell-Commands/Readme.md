### N o T e S 

---

#### Older methods : 

os.system()
os.popen()
os.spawn()

### Subprocess module : 

- Provides more powerful ways to manage and communicate with subprocesses.

```py
MAIN APIs 

* run() --> runs a command 
* popen() --> a class for flexibly executing a command in a new process.
```

```py
import subprocess
subprocess.run("ls")
subprocess.run("python3 test.py") //gives an error as file not found
Use subprocess.run(["python3","test.py"])
```

### Run commands and read output

```py
subprocess.run("ls", stdout=subprocess.PIPE)

--> result = subprocess.run("ls", stdout=subprocess.PIPE)
print(result.stdout.decode())

subprocess.run("ls", stdout=subprocess.PIPE, stderr=subprocess.PIPE)

Since python3.7
subprocess.run("ls",capture_output=true)
```

### Run commands by passing single strings 

`args` --> It is required for all calls and should be a string, sequence of program arguments.  
If passing a single string with argument we need to put shell = true otherwise it will treat it as the name of file to be executed.

```py
user_input="a.txt"
command = "cat{}".format(user_input)
subprocess.run(command,shell=true,capture_output=true)

## Vuln --> Shell Injection example ;pwd

Soln --> 

import shlex
shlex.quote(user_input) --> it will quote the input in case of vulnerability
```
