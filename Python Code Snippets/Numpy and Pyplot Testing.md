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
