---
title: "Clojure Collections"
date: 2023-10-06T06:08:21+05:30
draft: false 
weight: 11
next: symbols-bindings
---

The collections are necessary utils to organize and access data.

### Lists
These are collection of things in a given order, To create them, a quote needs
to be put in front of parens. "Commas" are optional and are not idiomatic.
```clojure
'(1 2 "hello" :world)
;; -> (1 2 "hello" :world)
```

```clojure
'(1, 2, "hello", :world)
;; -> (1 2 "hello" :world)
```

### List manipulatio
Getting first element is as follows.
```clojure
(first '(1 2 "hello" :world))
;; -> 1
```
And remaining elements.
```clojure
(rest '(1 2 "hello" :world))
;; -> (2 "hello" :world)
```

Nesting of first and rest, to get to second element.
```clojure
(first (rest '(1 2 "hello" :world)))
;; -> 2
```

When list reaches the end, it produces () and first of it is nil.
```clojure
(rest (rest (rest (rest '(1 2 "hello" :world)))))
;; -> ()

(first (rest (rest (rest (rest '(1 2 "hello" :world))))))
;; -> nil
```

Building list with cons.
```clojure
(cons 64 '())
;; -> (64)

(cons 64 nil)
;; -> (64)

(cons 2 (cons 3 (cons 4 (cons 5 nil))))
;; -> (2 3 4 5)

'(1 2 3 4 5)
;; -> (1 2 3 4 5)
```

### Vectors
Vectors are identified by square brackets. 
```clojure
[1 2 "hello" :world]
;; -> [1 2 "hello" :world]
```

### Vector manipulation
Vectors have fast index access. 
```clojure
(nth [1 2 "hello" :world] 0)
;; -> 1
```

last element can be accessed as follows.
```clojure
(last [1 2 "hello" :world])
;; -> :world
```

first and rest works too.

```clojure
(first [1 2 "hello" :world])
;; -> 1

(rest [1 2 "hello" :world])
;; -> (2 "hello" :world)
```

### More operators

Getting number of elements.
```clojure
(count [1 2 "hello" :world])
;; -> 4

(count '(1 2 "hello" :world))
;; -> 4
```

Adding elements to list and a vector, elements are added to beginning of list.
```clojure
(conj [1 2 "hello"] :world)
;; -> [1 2 "hello" :world]

(conj '(1 2 "hello") :world)
;; -> (:world 1 2 "hello")
```

### Maps
Maps stores data in key-value pairs and are identified with curly braces and commas are optional.

```clojure
{:hello "world" :foo "bar"}
;; -> {:hello "world" :foo "bar"}
```

### Maps manipulation
Get values with *get*.
```clojure
(get {:hello "world"} :hello)
;; -> "world"


(get {:hello "world"} :foo "not found")
;; -> "not found"
```

with keyword as key, can be used as a function to fetch values.
```clojure
(:hello {:hello "world"})
;; -> "world"
```

The *keys* and *vals* return keys and values.
```clojure
(keys {:hello "world" :foo "bar"})
;; -> (:hello :foo)

(vals {:hello "world" :foo "bar"})
;; -> ("world" "bar")
```

The *assoc* is used to form new association.
```clojure
(assoc {:hello "worldd" :foo "bar"} :hello "world")
;; -> {:hello "world", :foo "bar"}
```

likewise removal is done with *dissoc*.
```clojure
(dissoc {:hello "world" :foo "bar"} :foo)
;; -> {:hello "world"}
```

### Sets
Sets are collection with no duplicates, and recognized by surrounding **#{}**.
```clojure
#{:hello :world "foo" "bar"}
;; -> #{:hello :world "foo" "bar"}

#{:hello :world "foo" "foo"}
;; -> IllegalArgumentException Duplicate key: "foo"
```

### Set Operations
*union* combines sets.
```clojure
(clojure.set/union #{:hello :world} #{:foo :bar})
;; -> #{:bar :hello :world :foo}
```

*difference* takes away the common elements.
```clojure
(clojure.set/difference #{:hello :world :foo :jack} #{:foo :bar})
;; -> #{:hello :world :jack}
```

*intersection* returns shared elements.
```clojure
(clojure.set/intersection #{:hello :world :foo :jack} #{:foo :bar})
;; -> #{:foo}
```

conversion from another type of collection to set. 
```clojure
(set [:hello :world :hello :world])
;; -> #{:hello :world}

(set {:hello "world" :foo "bar"})
;; -> #{[:foo "bar"] [:hello "world"]}
```

getting elements out of set.
```clojure
(get #{:hello :world} :hello)
;; -> :hello

(get #{:hello :world} :foo)
;; -> :nil

;; accessing directly by keyword and set itself as a function
(#{:hello :world} :hello)
;; -> :hello
```

To test presence of an element, with *contains?*,
```clojure
(contains? #{:hello :world} :hello)
;; -> true

(contains? #{:hello :world} :foo)
;; -> false
```

To add elements using *conj*.
```clojure
(conj #{:hello } :world)
;; -> #{:hello :world}
```

To remove elements usin *disj*.

```clojure
(disj #{:hello :world } :world)
;; -> #{:hello}
```

