I am a PhD student at the University of Washington, where I work with the
Programming Languages and Software Engineering (PLSE) group.
Click [here](https://uwplse.org) for more info.

Software tooling and programmer productivity are my main interests.
I enjoy tackling problems that programmers face _in practice_ in their
day-to-day work. To that end, I've gotten my feet wet in industry, ranging from
small startups with 4 backend developers, to behemoths like
[@twitter](https://github.com/twitter).

Before all that, I earned my Master's degree in Computer Science at
[@ubc](https://www.ubc.ca), where my thesis investigated how
[developers investigate data-flow reachability questions](https://open.library.ubc.ca/soa/cIRcle/collections/ubctheses/24/items/1.0421073?o=0).


```rkt
#lang racket

(define (sbc s)
  (local [(define (zip s)
            (for/list ([c s]
                       [i (build-list (string-length s) add1)])
              `(,i ,(string c))))
          (define (upcase-evens lop)
            (for/list ([p lop])
              (match p
                [`(,i ,c) (if (not (odd? i))
                              (string-upcase c)
                              c)])))]
    (apply string-append ((compose upcase-evens zip) s))))


(sbc "hello, world")
```
