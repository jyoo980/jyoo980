```Racket
(define (mystery str)
  (local [(define (zip lox)
            (map (λ (i x)
                   `(,i ,x))
                 (build-list (length lox) identity)
                 lox))
          (define (str->los str)
            (map string (string->list str)))]
    (foldl (λ (s acc) (string-append acc s)) ""
           (map (λ (p)
                  (match p
                    [`(,i ,s)
                     (if (= (modulo i 2) 0)
                         s
                         (string-upcase s))]))
                (zip (str->los str))))))
```
