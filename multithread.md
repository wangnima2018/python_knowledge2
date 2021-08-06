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


```
what's Queue.task_done()
https://stackoverflow.com/questions/49637086/python-what-is-queue-task-done-used-for

import logging
import queue
import threading
import time

items_queue = queue.Queue()
running = False


def items_queue_worker():
    while running:
        try:
            item = items_queue.get(timeout=0.01)
            if item is None:
                continue

            try:
                process_item(item)
            finally:
                items_queue.task_done()

        except queue.Empty:
            pass
        except:
            logging.exception('error while processing item')


def process_item(item):
    print('processing {} started...'.format(item))
    time.sleep(0.5)
    print('processing {} done'.format(item))


if __name__ == '__main__':
    running = True

    # Create 10 items_queue_worker threads
    worker_threads = 10
    for _ in range(worker_threads):
        threading.Thread(target=items_queue_worker).start()

    # Populate your queue with data
    for i in range(100):
        items_queue.put(i)

    # Wait for all items to finish processing
    items_queue.join()

    running = False

```
