## KeyError: 'content'

You are getting cryptic error messages when trying to plot (any `plot_trace` call):
```
Traceback (most recent call last):
File "/virt/lib/python3.12/site-packages/pyviz_comms/init.py", line 340, in _handle_msg
	self._on_msg(msg)
File "/virt/lib/python3.12/site-packages/panel/viewable.py", line 469, in _on_msg
	patch = manager.assemble(msg)
            ^^^^^^^^^^^^^^^^^^^^^
File "/virt/lib/python3.12/site-packages/panel/models/comm_manager.py", line 29, in assemble
	msg_obj = cls(header, msg['metadata'], msg['content'])
                                           ~~~^^^^^^^^^^^
KeyError: 'content'
```

### Solution

1. Save your work (`Ctrl + S`). Do this for all open notebooks.
2. Clear all outputs -> *Edit* -> *Clear Outputs of All Cells*.
3. Stop Jupyter Lab (or Notebook) -> *File* -> *Shut Down*.
4. Run `find . -name ".ipynb_checkpoints" -exec rm -r "{}" +` in the repository.
5. Start Jupyter Lab (or Notebook) back again:
   `python -m jupyter lab` or `python -m jupyter notebook`.

