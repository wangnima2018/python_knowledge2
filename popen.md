```
http://xstarcd.github.io/wiki/Python/python_subprocess_study.html

https://www.cnblogs.com/zhoug2020/p/5079407.html


```



```python3
example for poll:

import time
import subprocess

p = subprocess.Popen("sleep 15", shell=True)
# Better: p = subprocess.Popen(["sleep", "30"])

# Wait until process terminates
while p.poll() is None:
    time.sleep(1)
    print("p poll is None")

# It's done
print("Process ended, ret code:", p.returncode)
print('p poll now ' + str(p.poll()))

##########run output:
PENGs-MacBook-Pro:try_learn wupeng$ python3 popen_ex1.py
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
p poll is None
Process ended, ret code: 0
p poll now 0
```
