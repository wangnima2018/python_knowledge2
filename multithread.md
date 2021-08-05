```
code example1

class Sample(object):
    def __init__(self):
    
    def _run_process(self, cmd):
        try:
            self._device.shell(cmd)
        except Exception as ex:
            raise ex
    
    def start_process(self, customized_cmd):
        try:
            thread_handler = threading.Thread(target=self._run_process, args=[customized_cmd])
            thread_handler.daemon = True
            thread_handler.start()
            return thread_handler
        except ex:
            raise ex


```

```
example2:

import multiprocessing

def cal_square(numbers, cur_q):
    for n in numbers:
        cur_q.put(n*n)

if __name__ == "__main__":
    numbers = [2,3,5]
    cur_q = multiprocessing.Queue()
    p = multiprocessing.Process(target=cal_square, args=(numbers, cur_q))

    p.start()
    p.join()

    while not cur_q.empty():
        print(cur_q.get())
```
