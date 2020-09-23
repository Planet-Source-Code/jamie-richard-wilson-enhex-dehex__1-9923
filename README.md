<div align="center">

## EnHex / DeHex


</div>

### Description

EnHex converts a string to hexidecimal characters, which I designed for use with encryption routines that sometimes output unprintable characters. It's a simple way to convert unprintable characters into something printable. DeHex simply reverses the process.
 
### More Info
 
EnHex Input: normal text

DeHex Input: text that has been "en-hexed"

The assumption is that any text sent to DeHex is in fact hexidecimal. I pulled this from my own personal coding toolbox so I haven't built in any error checking because it was written for use in a very controlled environment -- such as apps I've written that use encryption.

EnHex Return: text converted into hexidecimal characters

DeHex Return: the original text that was converted to hexidecimal characters using EnHex

Converting a string into hexidecimal format will effectively double the size of the string (hexidecial requires two characters for every "en-hexed character), so be sure to weigh the benefits of having printable text against the size of the result. I tend to only use this if I need to send encrypted data blocks through email or if I want a user to manually enter small amounts of encrypted data, such as a one-line registration number.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jamie Richard Wilson](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jamie-richard-wilson.md)
**Level**          |Beginner
**User Rating**    |5.0 (30 globes from 6 users)
**Compatibility**  |VB 3\.0, VB 4\.0 \(16\-bit\), VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0, VB Script, ASP \(Active Server Pages\) 
**Category**       |[Encryption](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/encryption__1-48.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jamie-richard-wilson-enhex-dehex__1-9923/archive/master.zip)





### Source Code

```
Public Function EnHex(Data As String) As String
  Dim iCount As Double
  Dim sTemp As String
  For iCount = 1 To Len(Data)
    sTemp = Hex$(Asc(Mid$(Data, iCount, 1)))
    If Len(sTemp) < 2 Then sTemp = "0" & sTemp
    EnHex = EnHex & sTemp
  Next iCount
End Function
Public Function DeHex(Data As String) As String
  Dim iCount As Double
  For iCount = 1 To Len(Data) Step 2
    DeHex = DeHex & Chr$(Val("&H" & Mid$(Data, iCount, 2)))
  Next iCount
End Function
```

