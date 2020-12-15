```Haskell
import Data.Char

withIndex :: String -> [(Int, Char)]
withIndex s =
    let f [] acc _ = acc
        f (c:cs) acc n = f cs (acc ++ [(n, c)]) (n + 1)
    in f s [] 0

mystery :: String -> String
mystery s =
    let indexed = withIndex s
        f acc (n, c) =
            acc ++ if even n then map toUpper [c] else [c]
    in foldl f "" indexed
```
