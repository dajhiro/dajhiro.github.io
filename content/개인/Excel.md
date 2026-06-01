### LET()
```excel
=LET(
  val, VLOOKUP(A2, B:D, 2, 0),
  IF(val > 100, val * 0.9, val * 1.1)
)
```

LET을 사용한 INDEX-MATCH
```excel
=LET(
  pos, MATCH(A2, B:B, 0),
  INDEX(C:C, pos)
)
```

INDEX-MATCH
```excel
=INDEX(C:C, MATCH(A2, B:B, 0))
```

VLOOKUP