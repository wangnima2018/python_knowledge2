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

```
