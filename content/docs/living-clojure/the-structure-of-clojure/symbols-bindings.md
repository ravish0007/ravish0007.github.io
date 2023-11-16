---
title: "Symbols and Bindings"
date: 2023-09-28T06:08:21+05:30
draft: false
weight: 12
#next
---

### Symbols
Clojure symbols are references to values. (default namespace is user)
```clojure
(def foo "bar")
;; -> #'user/foo

foo
;; -> "bar"

user/foo
;; -> "bar"
```

*let* introduces scope and preserves original value, and expects pair of symbols
and values in vector form.

```clojure
(def foo "bar") 
;; -> #'user/foo

(let [foo "barx"] foo)
   ;; -> "barx"

foo
;; -> "bar"
```
* def to create global vars
* let to create temporary bindings
