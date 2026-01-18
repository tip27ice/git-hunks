# git-hunks

Non-interactive selective hunk staging for git. Designed for use by AI agents and scripts.

## Commands

### git hunks list

List all unstaged hunks with unique IDs:

```
$ git hunks list
src/main.c:@-10,6+10,7
@@ -10,6 +10,7 @@
 #include <stdio.h>
+#include <stdlib.h>
---
src/main.c:@-45,3+46,5
@@ -45,3 +46,5 @@
 return 0;
+return 1;
---
```

Use `--staged` to list staged hunks instead.

### git hunks add

Stage specific hunks by ID:

```
$ git hunks add 'src/main.c:@-10,6+10,7'
Staged: src/main.c:@-10,6+10,7
```

Hunk IDs use the format `file:@-old,len+new,len` based on the diff's `@@` header, so they remain stable even when other hunks are staged.

## Installation

```sh
make install
```

Or to install to a different prefix:

```sh
make PREFIX=~/.local install
```

## License

MIT
