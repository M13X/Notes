
Install Windows Terminal from Microsoft Store

Install-Module oh-my-posh -Scope CurrentUser

notepad/code $PROFILE

```
Import-Module oh-my-posh
##oh-my-posh prompt init
```

Set-ExecutionPolicy -ExecutionPolicy Unrestricted
```powershell
Install-Module -Name PSReadLine
```

Add to $PROFILE
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView

Starship