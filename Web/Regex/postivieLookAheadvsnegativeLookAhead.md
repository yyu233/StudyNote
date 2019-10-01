Positive lookahead with ?= peeks ahead to ensure that its subpattern could match.

```
> (regexp-match-positions #rx"grey(?=hound)"
    "i left my grey socks at the greyhound")
'((28 . 32))
```
The regexp ```#rx"grey(?=hound)"``` matches grey, but only if it is followed by hound. Thus, the first grey in the text string is not matched.

Negative lookahead with ?! peeks ahead to ensure that its subpattern could not possibly match.
```
> (regexp-match-positions #rx"grey(?!hound)"
    "the gray greyhound ate the grey socks")
'((27 . 31))
```
The regexp ```#rx"grey(?!hound)" ```matches grey, but only if it is not followed by hound. Thus the grey just before socks is matched.
