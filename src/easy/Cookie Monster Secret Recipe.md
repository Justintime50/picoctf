# Cookie Monster Secret Recipe

Inspecting the cookies for the site gives us a base64 encoded value that is URL parsed.

```text
secret_recipe - cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzc3MUQ1RUIwfQ%3D%3D
```

We can first unquote the URL:

```python
from urllib.parse import unquote

unquote('cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzc3MUQ1RUIwfQ%3D%3D')
```

This gives us `cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzc3MUQ1RUIwfQ==`

We can then decode this:

```python
import base64

base64.b64decode('cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzc3MUQ1RUIwfQ==')
```

This provides the flag.
