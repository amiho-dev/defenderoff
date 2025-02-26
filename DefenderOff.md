reg delete "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /f
reg delete "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender Security Center" /f
reg delete "HKLM\SOFTWARE\Policies\Microsoft\Windows\System" /v "EnableSmartScreen" /f
reg delete "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies" /f
gpupdate /force


cmd:
sc config WinDefend start= auto
sc start WinDefend
sc config SecurityHealthService start= auto
sc start SecurityHealthService

restart.
