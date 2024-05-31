## KeyError: 'content'

You are getting cryptic error messages when trying to plot:
```
...
msg_obj = cls(header, msg['metadata'], msg['content'])
KeyError: 'content'
```

**Solution**: Remove the virtual environment and reinstall it.
