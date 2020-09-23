<div align="center">

## hide\\show


</div>

### Description

this simple code can hide\show your clock, start button, tray icons, taskbar, and desktop. Please vote!!!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[sck](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/sck.md)
**Level**          |Intermediate
**User Rating**    |4.8 (53 globes from 11 users)
**Compatibility**  |VB 4\.0 \(16\-bit\), VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__1-1.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/sck-hide-show__1-13197/archive/master.zip)

### API Declarations

```
Private Declare Function ShowWindow Lib "user32" (ByVal hwnd As Long, ByVal nCmdShow As Long) As Long
Private Declare Function FindWindow Lib "user32" Alias "FindWindowA" (ByVal lpClassName As String, ByVal lpWindowName As String) As Long
Private Declare Function FindWindowEx Lib "user32" Alias "FindWindowExA" (ByVal hWnd1 As Long, ByVal hWnd2 As Long, ByVal lpsz1 As String, ByVal lpsz2 As String) As Long
```


### Source Code

```
Private Declare Function FindWindow Lib "user32" Alias "FindWindowA" (ByVal lpClassName As String, ByVal lpWindowName As String) As Long
Private Declare Function FindWindowEx Lib "user32" Alias "FindWindowExA" (ByVal hWnd1 As Long, ByVal hWnd2 As Long, ByVal lpsz1 As String, ByVal lpsz2 As String) As Long
Private Declare Function ShowWindow Lib "user32" (ByVal hwnd As Long, ByVal nCmdShow As Long) As Long
Sub Hide_Clock()
ShowWindow FindWindowEx(FindWindowEx(FindWindow("Shell_TrayWnd", vbNullString), 0&, "TrayNotifyWnd", vbNullString), 0&, "TrayClockWClass", vbNullString), 0
End Sub
Sub Hide_Desktop()
ShowWindow FindWindowEx(FindWindowEx(FindWindow("Progman", vbNullString), 0&, "SHELLDLL_DefView", vbNullString), 0&, "SysListView32", vbNullString), 0
End Sub
Sub Hide_StartButton()
ShowWindow FindWindowEx(FindWindow("Shell_TrayWnd", vbNullString), 0&, "Button", vbNullString), 0
End Sub
Sub Hide_TaskBar()
ShowWindow FindWindow("Shell_TrayWnd", vbNullString), 0
End Sub
Sub Hide_Tray()
ShowWindow FindWindowEx(FindWindow("Shell_TrayWnd", vbNullString), 0&, "TrayNotifyWnd", vbNullString), 0
End Sub
Sub Show_Clock()
ShowWindow FindWindowEx(FindWindowEx(FindWindow("Shell_TrayWnd", vbNullString), 0&, "TrayNotifyWnd", vbNullString), 0&, "TrayClockWClass", vbNullString), 5
End Sub
Sub Show_Desktop()
ShowWindow FindWindowEx(FindWindowEx(FindWindow("Progman", vbNullString), 0&, "SHELLDLL_DefView", vbNullString), 0&, "SysListView32", vbNullString), 5
End Sub
Sub Show_StartButton()
ShowWindow FindWindowEx(FindWindow("Shell_TrayWnd", vbNullString), 0&, "Button", vbNullString), 5
End Sub
Sub Show_TaskBar()
ShowWindow FindWindow("Shell_TrayWnd", vbNullString), 5
End Sub
Sub Show_Tray()
ShowWindow FindWindowEx(FindWindow("Shell_TrayWnd", vbNullString), 0&, "TrayNotifyWnd", vbNullString), 5
End Sub
```

