# [J][jsoftware]
## Apply function to array(s)
```
f =: - : -

u =: 1 2 3 4 5
v =: 6 7 8 9 10

f u NB. => _1 _2 _3 _4 _5
f v NB. => _6 _7 _8 _9 _10

u f v NB. => 5 5 5 5 5
v f u NB. => _5 _5 _5 _5 _5
```

## Apply function to subarrays
```
f =: -/&> NB. Subtract values in subarrays

X =: 1 2 ; 3 4 ; 5 6
f X NB. => _1 _1 _1
```

[jsoftware]: https://www.jsoftware.com/
