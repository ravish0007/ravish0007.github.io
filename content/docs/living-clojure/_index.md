---
title: Living Clojure
type: docs
# prev: docs/screen-orientation
next: structure-of-clojure
sidebar:
  open: true
---

<a href="https://clojure.org">Clojure</a> targets JVM, hence make sure java is installed.

```
java --version
```

Following is my JDK version.

```
openjdk 11.0.20.1 2023-08-24
OpenJDK Runtime Environment (build 11.0.20.1+1)
OpenJDK 64-Bit Server VM (build 11.0.20.1+1, mixed mode)
```

Next up, install leiningen

a) Create a project

```
lein new lalaland
```

b) CD into that

```
cd lalaland
```

c) Get the clojure REPL by running following command

```
lein repl
```

The above command shall give you repl and looks similar down below.

```

nREPL server started on port 39187 on host 127.0.0.1 - nrepl://127.0.0.1:39187
REPL-y 0.5.1, nREPL 1.0.0
Clojure 1.11.1
OpenJDK 64-Bit Server VM 11.0.20.1+1
    Docs: (doc function-name-here)
          (find-doc "part-of-name-here")
  Source: (source function-name-here)
 Javadoc: (javadoc java-object-or-class-here)
    Exit: Control+D or (exit) or (quit)
 Results: Stored in vars *1, *2, *3, an exception in *e

lalaland.core=>
```

FIN
