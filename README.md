I am currently working toward a Master's degree in Computer Science at [@ubc](https://www.ubc.ca).
Most recently, I worked as a software developer intern with the Privacy and Data Protection Engineering team at 
[@twitter](https://github.com/twitter). Before that, I was a software developer intern at
[@hootsuite](https://www.hootsuite.com/). For experience before that, check out my LinkedIn.

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
