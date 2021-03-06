---
title: "MSFT_DSCLocalConfigurationManager 類別的 ResourceGet 方法"
ms.date: 2016-05-16
keywords: "PowerShell，DSC"
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: c915ebd021ed20209bc491505d45cff2ac89f21d
ms.openlocfilehash: 1666b85402f17230090f7290c8cb400dd9fbf0a6

---

# MSFT_DSCLocalConfigurationManager 類別的 ResourceGet 方法

直接呼叫 DSC 資源的 **Get** 方法。

語法
------

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

參數
----------

*ResourceType* \[in\]  
要呼叫的資源名稱。

*ModuleName* \[in\]  
包含要呼叫之資源的模組名稱。

*resourceProperty* \[in\]  
在雜湊表中指定資源的屬性名稱與其值，分別作為索引鍵和值。 使用 [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) Cmdlet，探索資源的屬性和其類型。

*configurations* \[out\]  
傳回時，包含設定的內嵌執行個體。

## 傳回值
------------

若成功即傳回零；否則傳回錯誤碼。

## 備註

此為靜態方法。

## 需求
------------
>**MOF：**DscCore.mof

>**Namespace**：Root\Microsoft\Windows\DesiredStateConfiguration


## 另請參閱


[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)


 

 






<!--HONumber=Aug16_HO3-->


