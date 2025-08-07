# SSTI1

This is a server-side template injection attack.

I tried normal input:

```text
hello world
```

Which worked, then tried a template:

```python
{{ 7*7 }}
```

Which produced 49. We're in! Jinja is in use through inspection of the response headers (shows Python).

Printed out `self`, found there was a `TemplateReference` object. If we print the `__globals__` for that object we find we can use builtins such as `os` and eventually `popen` to run subprocess commands. With `ls` we found there was a `flag` file. All that's left is to print the contents and we retrieve our flag:

```python
{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat flag').read() }}
```
