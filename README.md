# Nim New Backend Template

- Template to create a new Backend for Nim, based on the JavaScript Backend.
- **Edit 4 files only to create your new Nim Backend**, as minimal as possible.
- As example it implements a new Python Backend *(unfinished, PR Welcome)*.


# Use

```
$ git clone https://github.com/juancarlospaco/nim-new-backend.git
```

- Hack code.

```console
$ git clone https://github.com/nim-lang/Nim.git
$ ls
Nim  nim-new-backend

$ cp --verbose --force nim-new-backend/compiler/jsgen.nim Nim/compiler/jsgen.nim
'nim-new-backend/compiler/jsgen.nim' -> 'Nim/compiler/jsgen.nim'

$ cp --verbose --force nim-new-backend/compiler/jstypes.nim Nim/compiler/jstypes.nim
'nim-new-backend/compiler/jstypes.nim' -> 'Nim/compiler/jstypes.nim'

$ cp --verbose --force nim-new-backend/lib/system/jssys.nim Nim/lib/system/jssys.nim
'nim-new-backend/lib/system/jssys.nim' -> 'Nim/lib/system/jssys.nim'

$ cp --verbose --force nim-new-backend/lib/system/reprjs.nim Nim/lib/system/reprjs.nim
'nim-new-backend/lib/system/reprjs.nim' -> 'Nim/lib/system/reprjs.nim'

$ cd Nim
$ sh ./build_all.sh
$ echo "echo 42" > example.nim
$ ./koch temp js -d:release -d:danger example.nim
```

- Open `example.js`. A new Nim compiler binary executable will be saved to `./bin/nim`.
- Hack code until you get valid code generated, then compile the Nim compiler again.

```console
$ ./koch temp js -d:release -d:danger example.nim
```

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

It is the second on popularity behind JavaScript, but Nim already has JavaScript.

To clean up code because JavaScript is kinda weird which also makes codegen weird.

I imagine creating a Ruby or Go Backend from a Python backend is easier than from C.
