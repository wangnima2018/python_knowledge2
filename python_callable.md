```
https://stackoverflow.com/questions/111234/what-is-a-callable

A callable is an object allows you to use round parenthesis () and eventually pass some parameters, just like functions.

Every time you define a function python creates a callable object. In example, you could define the function func in these ways (it's the same):

class a(object):
    def __call__(self, *args):
        print 'Hello'

func = a()

# or ... 
def func(*args):
    print 'Hello'
You could use this method instead of methods like doit or run, I think it's just more clear to see obj() than obj.doit()



```
