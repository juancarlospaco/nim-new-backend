# Nim New Backend Template

- Template to create a new Backend for Nim, based on the JavaScript Backend.
- **Edit 5 files only to create your new Nim Backend**, as minimal as possible.
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

$ cp --verbose --force nim-new-backend/lib/js/jscore.nim Nim/lib/js/jscore.nim
'nim-new-backend/lib/js/jscore.nim' -> 'Nim/lib/js/jscore.nim'

$ cp --verbose --force nim-new-backend/lib/system/jssys.nim Nim/lib/system/jssys.nim
'nim-new-backend/lib/system/jssys.nim' -> 'Nim/lib/system/jssys.nim'

$ cp --verbose --force nim-new-backend/lib/system/reprjs.nim Nim/lib/system/reprjs.nim
'nim-new-backend/lib/system/reprjs.nim' -> 'Nim/lib/system/reprjs.nim'

$ cd Nim
$ sh ./build_all.sh
$ koch boot
$ echo "echo 42" > example.nim
$ bin/nim js -d:release -d:danger example.nim
```

- Open `example.js`.
- Hack code until you get valid code generated, then compile the Nim compiler again.

```console
$ koch boot
$ bin/nim js -d:release -d:danger example.nim
```

**Optional:**
Rename `example.js` to the proper file extension you are compiling to,
example `mv example.js example.py`.


# FAQ

- Why not use Git SubRepos or Git SubTrees or Git SubModules?.

If you know Git SubRepos and Git SubTrees and Git SubModules,
you wont need this simplified repo.

- Why not use SymLinks?.

It may produce errors on `import` and `include`.

- Why Python?.

It is the second on popularity behind JavaScript, but Nim already has JavaScript.
