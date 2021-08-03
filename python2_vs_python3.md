```
In python3, there are two types: bytes and str
In python2, there are two types: unicode and str


In python3, bytes contains sequences of 8-bit values, str contains sequences of unicode chars. 
In python2, str contains sequence of 8-bit values, unicode contains sequence of Unicode chars. 

python2 unicode ---> python3 str.
python2 str ---> python3 bytes


python3 (convert str or bytes to str):
def to_str(bytes_or_str):
    if isinstance(bytes_or_str, bytes):
        value = bytes_or_str.decode('utf-8')
    else:
        value = bytes_or_str
    return value

python3 (convert str or bytes to str):
def to_bytes(bytes_or_str):
    if isintance(bytes_or_str, str):
        value = bytes_or_str.encode('utf-8')
    else:
        value = bytes_or_str
    return value


python2 (unicode or str to unicode):
def to_unicode(unicode_or_str):
    if isinstance(unicode_or_str, str):
        value = unicode_or_str.decode('utf-8')
    else:
        value = unicode_or_str
    return value
 
 python2 (str or unicode to str):
 def to_str(unicode_or_str):
     if isinstance(unicode_or_str, unicode):
         value = unicode_or_str.encode('utf-8')
     else:
         value = unicode_or_str
     return value

```
