---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,cmdlet,組件庫"
ms.date: 2016-10-14
contributor: manikb
title: psget_update script
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: 8c5211a51a9ff8bce641fde8deacd2d288916602

---

# Update-Script

Update-Script Cmdlet 可讓您使用 Install-Script Cmdlet 就地更新已安裝的指令碼檔案。

## 描述

Update-Script Cmdlet 會更新先前從中安裝之存放庫中所指定的指令碼。

## Cmdlet 語法

```powershell
Get-Command -Name Update-Script -Module PowerShellGet -Syntax
```
## Cmdlet 線上說明參考資料

[Update-Script](http://go.microsoft.com/fwlink/?LinkId=619787)

## 範例命令
```powershell
Install-Script -Name Fabrikam-Script -RequiredVersion 1.0 -Repository GalleryINT -Scope
Get-InstalledScript -Name Fabrikam-Script
Version Name Type Repository Description
------- ---- ---- ---------- -----------
1.0 Fabrikam-Script Script GalleryINT Description for the Fabrikam-Script script

# Update a specific script to the required version
Update-Script -Name Fabrikam-Script -RequiredVersion 1.5
Get-InstalledScript -Name Fabrikam-Script
Version Name Type Repository Description
------- ---- ---- ---------- -----------
1.5 Fabrikam-Script Script GalleryINT Description for the Fabrikam-Script script

# Update all installed scripts
Install-Script -Name Fabrikam-ServerScript -RequiredVersion 1.0 -Repository GalleryINT -Scope CurrentUser
Get-InstalledScript
Version Name Type Repository Description
------- ---- ---- ---------- -----------
2.0 Required-Script3 Script GalleryINT Description for the Required-Script3 script
1.0 Demo-Script Script LocalRepo1 Script file description goes here
1.5 Fabrikam-Script Script GalleryINT Description for the Fabrikam-Script script
1.0 Fabrikam-ServerScript Script GalleryINT Description for the Fabrikam-ServerScript script
2.5 Required-Script1 Script GalleryINT Description for the Required-Script1 script
2.5 Required-Script2 Script GalleryINT Description for the Required-Script2 script
2.0 Script-WithDependencies2 Script GalleryINT Description for the Script-WithDependencies2 script

Update-Script
Get-InstalledScript
Version Name Type Repository Description
------- ---- ---- ---------- -----------
2.5 Required-Script3 Script GalleryINT Description for the Required-Script3 script
1.0 Demo-Script Script LocalRepo1 Script file description goes here
2.5 Fabrikam-Script Script GalleryINT Description for the Fabrikam-Script script
2.5 Fabrikam-ServerScript Script GalleryINT Description for the Fabrikam-ServerScript script
2.5 Required-Script1 Script GalleryINT Description for the Required-Script1 script
2.5 Required-Script2 Script GalleryINT Description for the Required-Script2 script
2.0 Script-WithDependencies2 Script GalleryINT Description for the Script-WithDependencies2 script
```




<!--HONumber=Oct16_HO2-->


