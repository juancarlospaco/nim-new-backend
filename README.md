# Nim New Backend Template

- Template to create a new Backend for Nim, based on the JavaScript Backend.
- **Edit 4 files only to create your new Nim Backend**, as minimal as possible.
- As example it implements a new Python Backend *(unfinished, PR Welcome)*.


# Use

```console
$ git clone https://github.com/juancarlospaco/nim-new-backend.git
$ cd nim-new-backend
$ git clone https://github.com/nim-lang/Nim.git

$ cp --verbose --force compiler/jsgen.nim Nim/compiler/jsgen.nim
'compiler/jsgen.nim' -> 'Nim/compiler/jsgen.nim'

$ cp --verbose --force compiler/jstypes.nim Nim/compiler/jstypes.nim
'compiler/jstypes.nim' -> 'Nim/compiler/jstypes.nim'

$ cp --verbose --force lib/system/jssys.nim Nim/lib/system/jssys.nim
'lib/system/jssys.nim' -> 'Nim/lib/system/jssys.nim'

$ cp --verbose --force lib/system/reprjs.nim Nim/lib/system/reprjs.nim
'lib/system/reprjs.nim' -> 'Nim/lib/system/reprjs.nim'

$ nim c Nim/koch.nim
$ Nim/koch temp js -d:release -d:danger -d:nodejs example.nim
```

- Open `example.js`. A new Nim compiler binary executable will be saved to `./Nim/bin/nim`.
- Hack code until you get valid code generated, then compile the Nim compiler again.

```console
$ Nim/koch temp js -d:release -d:danger -d:nodejs example.nim
```

**Code to look at:**
See the dependency file generator, is a minimal working codegen:

- https://github.com/nim-lang/Nim/blob/devel/compiler/depends.nim


**Optional:**
Rename `example.js` to the proper file extension you are compiling to,
example `mv example.js example.py`.


# Example

```nim
echo 42
```
:arrow_up: Nim :arrow_up: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; :arrow_down: Python :arrow_down:
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
# Powered by Nim v1.1.1 https://nim-lang.org
import sys
from typing import *
sys.dont_write_bytecode: Bool = True  # type: Bool
print(str("42"))
```


# Requisites

- [Nim](https://nim-lang.org)


# FAQ

- Why not use Git SubRepos or Git SubTrees or Git SubModules?.

If you know Git SubRepos and Git SubTrees and Git SubModules,
then you wont need this simplified repo.

But if you have an idea to make this *less* complex, not more complex, then send PR.

- Why not use SymLinks?.

It may produce errors on `import` and `include`.

- But it generates a `*.js`?.

Yes, but file extensions, tutorials, documentation, cosmetics, etc can be left for last details.

- Why Python?.

It is the second on popularity behind JavaScript, but [Nim](https://nim-lang.org) [already has JavaScript.](https://nim-lang.org/docs/backends.html#backends-the-javascript-target)

To clean up code because JavaScript is kinda weird which also makes codegen weird.

I imagine creating a Ruby or Go Backend from a Python backend is easier than from C.
