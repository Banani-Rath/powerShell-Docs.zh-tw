---
title: "DSC WindowsOptionalFeature 資源"
ms.date: 2016-05-24
keywords: "PowerShell，DSC"
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 97714d3fa9a1c00fb3d2e79cc873280ca945a840
ms.openlocfilehash: 1254037b655a3160c90e69971c9faf061f205917

---

# DSC WindowsOptionalFeature 資源

> 適用於：Windows PowerShell 5.0

Windows PowerShell 預期狀態設定 (DSC) 的 **WindowsOptionalFeature** 資源提供一個機制，確保可在目標節點上啟用選用功能。

## 語法

```
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Ensure = [string] { Absent | Present }  ]
    [ Source = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    
}
```

## [內容]

|  屬性  |  描述   | 
|---|---| 
| 名稱| 表示您想要確保啟用或停用的功能名稱。| 
| Ensure| 指定是否啟用功能。 若要確保啟用功能，請將這個屬性設為 "Present"。若要確保停用功能，請將屬性設為 "Absent"。|
| 來源| 未實作。|
| NoWindowsUpdateCheck| 指定在搜尋來源檔案以啟用功能時，DISM 是否連絡 Windows Update (WU)。 如果是 $true，則 DISM 不連絡 WU。|
| RemoveFilesOnDisable| 停用時 (亦即 **Ensure** 設為 "Absent")，設為 **$true** 會移除所有與此功能相關聯的檔案。|
| LogLevel| 記錄中顯示的最大輸出等級。 接受的值包括："ErrorsOnly" (僅記錄錯誤)、"ErrorsAndWarning" (記錄錯誤與警告)，以及 "ErrorsAndWarningAndInformation" (記錄錯誤、警告和偵錯資訊)。|
| LogPath| 要讓資源提供者記錄作業的記錄檔路徑。| 
| DependsOn| 指定必須先執行另一項資源的設定，再設定這項資源。 例如，如果第一個想要執行的資源設定指令碼區塊的識別碼是 __ResourceName__，而它的類型是 __ResourceType__，則使用這個屬性的語法就是 `DependsOn = "[ResourceType]ResourceName"`。| 
 






<!--HONumber=Aug16_HO3-->


