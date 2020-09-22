<div align="center">

## New type of INI


</div>

### Description

A different kind of INI because I don't like the

ini's that are so easy to use!

example:

@ Header1, Value1

@ Header2, Value2

@ Header3, Value3

@ Header4, Value4
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Cody Rutkowski](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/cody-rutkowski.md)
**Level**          |Intermediate
**User Rating**    |3.3 (20 globes from 6 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[Files/ File Controls/ Input/ Output](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/files-file-controls-input-output__1-3.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/cody-rutkowski-new-type-of-ini__1-27925/archive/master.zip)





### Source Code

```
<PRE>
Public Function ReadFile(Header$, Filename$)
Dim FF: FF = FreeFile
Dim Data$
Open Filename$ For Binary As #FF
  Data$ = Input(LOF(FF), FF)
Close #FF
Dim lines: lines = Split(Data$, vbCrLf)
For i = 0 To UBound(lines)
  If UCase(Left(lines(i), Len("@ " & Header & ","))) = UCase("@ " & Header & ",") Then
    ReadFile = Mid(lines(i), Len("@ " & Header & ",") + 1)
    ReadFile = LTrim(ReadFile)
  End If
Next i
End Function
</PRE>
```

