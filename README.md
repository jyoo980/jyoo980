I am currently working toward a Masters degree in Computer Science at [@ubc](https://www.ubc.ca).
Most recently, I worked as a software developer intern with the Privacy and Data Protection Engineering team at 
[@twitter](https://github.com/twitter), endeavouring to make data at Twitter usable, discoverable, and compliant.
Before that, I was a software developer intern at [@hootsuite](https://www.hootsuite.com/).

If you can tell me what the code below evaluates to, chances are we're gonna get along great

```racket
#lang racket

(define (sbc s)
  (local [(define (zip s)
            (for/list ([c s]
                       [i (build-list (string-length s) add1)])
              `(,i ,(string c))))
          (define (upcase-odds lop)
            (for/list ([p lop])
              (match p
                [`(,i ,c) (if (odd? i)
                              (string-upcase c)
                              c)])))]
    (apply string-append ((compose upcase-odds zip) s))))


(sbc "hello, world")
```
