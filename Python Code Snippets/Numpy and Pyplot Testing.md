## Code Emitter Coding Blocks
### Test Code Basics
- Try to get `numpy and matplotlib.pyplot` working
- Make sure to use `import micropip` to help install by running `await micropip.install('dependancy')` 
- then we can import the `dependancy` like `numpy` or `matplotlib` to the code

```python

print("hello World!")
```

```python
import micropip
await micropip.install('numpy')
import numpy as np

a = np.random.rand(20, 1)

print(a)
```

```python
import micropip
await micropip.install('matplotlib')

import matplotlib.pyplot as plt

fix, ax = plt.subplots()
ax.plot([1,2,3,4],[1,4,2,3])
plt.show()
```

### Working Code to get File Data
- We need to use `from js import app` to access the Obsidian Vault API
- Then from the API we can do `app.vault.getAbstractFilePath(path)` with path being a localized path in the vault e.g. specify highest level folder in vault
- Then we just do `app.vault.read(file)` and `content = await result` because we need to use `await` for this

```python
import micropip
await micropip.install('numpy')
import numpy as np
from js import app

tfile = app.vault.getAbstractFileByPath(
"Python Code Snippets/player_item_data.md"
)

text_promise = app.vault.read(tfile)
content = await text_promise
print(content, '\n')
```

## Execute Code Plugin Blocks
### testing stuff

```python

import numpy as np

a = np.random.rand(20, 1)

print(a)
```
### Testing Basic Parts
```python
import numpy as  np
import matplotlib.pyplot as plt

def main():
	print("hello world")

if __name__ == "__main__":
	main()
```
```output
hello world
```

### Reading another file
```python
import os
import csv
import matplotlib.pyplot as plt
from datetime import datetime
from collections import Counter

def main():
    vault = @vault_path
    rel   = "Python Code Snippets/player_item_data.md"
    fn    = os.path.join(vault, rel)

    with open(fn, encoding="utf-8") as f:
        tbl = [line.rstrip() for line in f if line.lstrip().startswith("|")]

    data_lines = tbl[2:]
    csv_lines = []

    for row in data_lines:
        fields   = [cell.strip() for cell in row.strip().strip("|").split("|")]
        csv_line = ",".join(fields)
        csv_lines.append(csv_line)
        print(csv_line)

if __name__ == "__main__":
    main()
