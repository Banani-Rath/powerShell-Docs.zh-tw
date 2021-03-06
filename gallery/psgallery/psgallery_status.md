---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,cmdlet,組件庫"
ms.date: 2016-10-14
contributor: manikb
title: psgallery_status
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: 69df41ae0a9dfd9fb71655cf6334f60f1d39ae94

---

PowerShell 資源庫狀態
=========================


## 2016/8/10 - 已解決︰無法傳送電子郵件給 cgadmin@microsoft.com

__影響摘要__：2016/8/5 到 2016/8/10 之間，客戶無法傳送電子郵件給 cgadmin@microsoft.com，也無法使用 [與我們連絡] 功能。  
__根本原因__︰工程師確認原因出自電子郵件帳戶的設定變更。  
__解決方法__︰工程師已找出解決此設定問題的方法。  
__後續步驟__︰若您曾在這段期間使使用 [與我們連絡] 連結，或傳送郵件給 cgadmin@microsoft.com，但我們未回應，請再試一次。 感謝您的耐心配合。



## 2016/7/13 -下載項目失敗

__影響摘要__：2016/7/11 到 2016/7/13 之間，有一些客戶出現無法從 PowerShell 資源庫下載項目的問題。 此問題可能會顯示在 Install-Module/Install-Script 與 Save-Module/Save-Script 傳回的下列錯誤訊息中︰

```PowerShell
PS C:\> Install-Module xStorage 
PackageManagement\Install-Package : Package 'xStorage' failed to be installed because: 
End of Central Directory record could not be found. At C:\Program 
Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1375 char:21 + ... 
$null = PackageManagement\Install-Package @PSBoundParameters + 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ + CategoryInfo : InvalidResult: 
(xStorage:String) [Install-Package], Exception + FullyQualifiedErrorId : Package '{0}' 
failed to be installed because: {1},Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage 
```

__初步的根本原因__︰工程師確認這是 Azure 內容傳遞網路 (CDN) 的問題。Azure CDN 於 2016/7/11 部署到 PowerShell 資源庫。  
__緩和方法__：工程師停用了 PowerShell 資源庫中的 Azure CDN。  
__後續步驟__︰調查最根本的原因，並制定解決方法，以避免日後再次發生。


## 2016/5/19 - 下載項目失敗
__影響摘要__：2016/5/17 到 2016/5/19 之間，有一些客戶出現無法從 PowerShell 資源庫下載項目的問題。 此問題可能會顯示在 Install-Module/Install-Script 與 Save-Module/Save-Script 傳回的下列錯誤訊息中︰

```PowerShell
VERBOSE: Hash for package 'AzureRM.OperationalInsights' does not match hash provided from the server.
VERBOSE: InstallPackageLocal' - name='AzureRM.OperationalInsights', version='1.0.8',
destination='C:\Users\jbritt\AppData\Local\Temp\2\1741355729'
WARNING: Package 'AzureRM.OperationalInsights' failed to be installed because: 
End of Central Directory record could not be found. 
WARNING: Dependent Package 'AzureRM.OperationalInsights' failed to install. 
WARNING: Package 'AzureRM' failed to install. 
VERBOSE: Module 'AzureRM.Network' was saved successfully. 
VERBOSE: Saving the dependency module 'AzureRM.NotificationHubs' with version '1.0.8' for the 
module 'AzureRM'. 
VERBOSE: Module 'AzureRM.NotificationHubs' was saved successfully. 
PackageManagement\Save-Package : Unable to save the module 'AzureRM'. At C:\Program 
Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1187 char:21 + 
$null = PackageManagement\Save-Package @PSBoundParameters + 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ + 
CategoryInfo : InvalidOperation: (Microsoft.Power...ets.SavePackage:SavePackage) 
[Save-Package], Exception + FullyQualifiedErrorId : ProviderFailToDownloadFile,
Microsoft.PowerShell.PackageManagement.Cmdlets.SavePackage 
```

__初步的根本原因__︰工程師確認是 Azure 內容傳遞網路 (CDN)基礎提供者中斷所致。Azure CDN 於 2016/5/17 部署到 PowerShell 資源庫。  
__緩和方法__：工程師停用了 PowerShell 資源庫中的 Azure CDN。  
__後續步驟__︰調查最根本的原因，並制定解決方法，以避免日後再次發生。




<!--HONumber=Oct16_HO2-->


