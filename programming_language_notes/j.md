# [J][jsoftware]
## Apply function to subarrays
```j
f =: -/&> NB. Subtract values in subarrays

X =: 1 2 ; 3 4 ; 5 6
f X NB. => _1 _1 _1
```

## [Valence][valence]: Monadic, Dyadic, and Ambivalent functions
```j
u =: 1 + i.5
v =: 10 + u

NB. =============================================
NB. Square root
m =: 3 : 0 
  %: y
) NB. strictly monadic

m u NB. => 1 1.41421 1.73205 2 2.23607
m v NB. => 3.31662 3.4641 3.60555 3.74166 3.87298

NB. =============================================
NB. n-root
d =: 4 : 0
  x %: y
) NB. strictly dyadic

u d v NB. => 11 3.4641 2.35133 1.93434 1.71877
v d u NB. => 1 1.05946 1.08818 1.10409 1.11326

NB. =============================================
NB. Negate monadic, divide dyadic
a =: - : % NB. ambivalent

a u NB. => _1 _2 _3 _4 _5
a v NB. => _11 _12 _13 _14 _15

u a v NB. => 0.0909091 0.166667 0.230769 0.285714 0.333333
v a u NB. => 11 6 4.33333 3.5 3
```

## License
<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

[jsoftware]: https://www.jsoftware.com/
[valence]: https://code.jsoftware.com/wiki/Vocabulary/Valence
