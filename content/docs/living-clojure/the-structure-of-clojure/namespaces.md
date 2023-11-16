---
title: "Namespaces"
date: 2023-09-28T06:08:21+05:30
draft: false
weight: 14
#next
---

Namespaces are organized and controlled access to vars. Creation and switching to new nampspace can be done with *ns*.

```clojure
(ns foo.bar)
```

Current namespace can be inspected as follows.
```clojure
*ns*
;; -> #<Namespace foo.bar>
```

Var definitions can be directly accessible or with fully qualified namespace.
```clojure
(def hello "world") 
;; -> #'foo.bar/hello

hello
;; -> "world"

foo.bar/hello
;; -> "world"
```

Switching to another namespace, the symbol will no longer be resolved.
Fully qualified namespace resolves the symbol.

```clojure
(ns diff.namespace) 
;; -> nil

hello
;; -> CompilerException java.lang.RuntimeException:
;; -> Unable to resolve symbol: hello in this contex

foo.bar/hello
;; -> "world"

```

If load a namespace, *require* is used.
```clojure
(require 'clojure.set)
```

Another way to do the above is to alias it.
```clojure
(ns lalaland)
;; -> nil

(require '[foo.bar :as fb])
;; -> nil

fb/hello
;; -> "world"
```

It is common to see nested in ns.
```clojure
(ns lalaland
    (:require [foo.bar :as fb]))

fb/hello
;; -> "world"
```
