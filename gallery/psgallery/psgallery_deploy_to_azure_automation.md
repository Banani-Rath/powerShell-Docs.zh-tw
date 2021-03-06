---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,cmdlet,組件庫"
ms.date: 2016-10-14
contributor: manikb
title: psgallery_deploy_to_azure_automation
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: c028bf6145b41c13bccda9543a782b838bd730ff

---

部署至 Azure 自動化
===========================

項目詳細資料頁面上的 [Deploy to Azure Automation] (部署至 Azure 自動化) 按鈕會將項目從 PowerShell Gallery 部署至 Azure 自動化。

![Deploy to Azure Automation (部署至 Azure 自動化) 按鈕](Images/DeployToAzureAutomationButton.png)

按一下時，會將您重新導向至使用 Azure 帳戶認證所登入的 Azure 管理入口網站。
如果項目包含相依性，則也會將所有相依性部署至 Azure 自動化。

警告︰如果相同的項目和版本已存在於您的自動化帳戶，則再次從 PowerShell Gallery 部署它將會覆寫自動化帳戶中的項目。

如果您部署模組，則它會出現在 [Azure 自動化] 的 [模組] 區段中。  如果您部署指令碼，則它會出現在 [Azure 自動化] 的 [Runbook] 區段中。

將 AzureAutomationNotSupported 標記新增至項目中繼資料，即可停用 [Deploy to Azure Automation] (部署至 Azure 自動化) 按鈕。

若要深入了解 Azure 自動化，請參閱 [Azure 自動化網站](http://azure.microsoft.com/en-us/services/automation/)。




<!--HONumber=Oct16_HO2-->


