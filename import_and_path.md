1 https://chrisyeh96.github.io/2017/08/08/definitive-guide-python-imports.html#case-examples

2 https://realpython.com/absolute-vs-relative-python-imports/

```python
a real example:
Here's the folder hierarchy:
robotframework
-src
-utest
|--api
|---test_run_and_rebot.py

If I want to run test_run_and_robot.py, I have 2 options
Op1:
import related code:
from utest.resources.runningtestcase import RunningTestCase
from utest.resources.Listener import Listener

Run test_run_and_rebot.py file from robotframework dir:
/Users/wupeng/projects_code/robotframework-master2/robotframework:   python3 test_run_and_rebot.py

The logic behind it is when python3 start with *.py file, that file's location will be put to sys.path

Op2:
import related code:
sys.path.append(os.path.abspath("."))
from utest.resources.runningtestcase import RunningTestCase
from utest.resources.Listener import Listener
sys.path.pop()

Since we run the file from dir:
 /Users/wupeng/projects_code/robotframework-master2/robotframework/utest/api/, if we check sys.path, we can observe:
 ['/Users/wupeng/projects_code/robotframework-master2/robotframework/utest/api',...]
 Since '/Users/wupeng/projects_code/robotframework-master2/robotframework' is missing from sys.path, we need to update it with code:
 sys.path.append(os.path.abspath("."))
 
```

