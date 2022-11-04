If you're looking for developers who care deeply about software tooling, developer productivity,
and helping solve hard problems that developers encounter, please get in touch.

I was a software engineer at [@twitter](https://github.com/twitter), working on the Privacy 
Tooling and Infrastructure team.
Before that, I earned my Master's degree in Computer Science at [@ubc](https://www.ubc.ca),
where my thesis investigated how [developers investigate data-flow reachability questions](https://open.library.ubc.ca/soa/cIRcle/collections/ubctheses/24/items/1.0421073?o=0).

If you can tell me what the code below evaluates to, chances are we're gonna get along great

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
