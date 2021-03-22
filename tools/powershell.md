## Powershell

Print variable:

```
Write-Host $var
```

Print string literal with variable:

```
Write-Host "Two" $r[$j]
```

Print string multiple times:

```
Write-Host $("A"*32)
> "A"*32
```

Print ASCII table:

```
1..128 | %{"$_ $([char]$_)"}
```