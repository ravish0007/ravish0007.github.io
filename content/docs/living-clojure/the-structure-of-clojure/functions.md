---
title: "Functions"
date: 2023-09-28T06:08:21+05:30
draft: false
weight: 13
next: namespaces
---

*defn* takes following arguments: the name of the function, a vector of parameters, and finally the body of the function. 

To call the function, simply use the function with parens. 

When we call a function, Clojure will evaluate it and return a result.
```clojure
(defn some-thing [] "one more thing") 
;; -> #'user/some-thing

(some-thing) 
;; -> "one more thing"
```

Following is a function with parameters.

```clojure
(defn some-thing [foo bar] {:name "apple"
:foo foo
:bar bar})
;; -> #'user/some-thing

(some-thing "yellow" "fields")
;; -> {:name "apple", :foo "yellow", :bar "fields"} 
```

Following is an anonymous function without a name, and are expressed with *fn* operator.
Those can be called with surrounding parens:


```clojure
(fn [] (str "Ahoy" "!"))
;; -> #object[lalaland.core$eval2436$fn__2437 0x40ce6a71 "lalaland.core$eval2436$fn__2437@40ce6a71"]

;;invoke with parens

((fn [] (str "Ahoy" "!")))
;; -> "Ahoy !"
```

*defn* =  *def* + *fn* 

```clojure
(def some-thing (fn [] (str "Ahoy " "!"))) 
;; -> #'user/some-thing

(some-thing)
;; -> "Ahoy !"
```

Following is shorthand form of an anonymous function. It uses a # in front.
```clojure
(#(str "Ahoy" "!"))
;; -> "Ahoy !"
```

For a single parameter, percent sign (%) to represents it.
```clojure
(#(str "Hello" %) "world")
;; -> "Hello world"
```

for multiple parameters, %1, %2 and so on represents the same

```clojure
(#(str "hello" %1 %2) "foo" "bar") 
;; -> "hello foo bar"
```













