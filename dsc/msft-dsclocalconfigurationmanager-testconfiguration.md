---
title: "MSFT_DSCLocalConfigurationManager 類別的 TestConfiguration 方法"
ms.date: 2016-05-16
keywords: "PowerShell，DSC"
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: c915ebd021ed20209bc491505d45cff2ac89f21d
ms.openlocfilehash: 0777467d37e2f5588f9c0ef368148e3bea963a5b

---


# MSFT_DSCLocalConfigurationManager 類別的 TestConfiguration 方法

將設定文件傳送到受管理的節點，並對文件驗證目前的設定。

語法
------

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

參數
----------

*configurationData* \[in\]  
設定的環境資料。

*InDesiredState* \[out\]  
傳回時，指定受管理的節點是否為設定文件所指定的狀態。

*ResourcesInDesiredState* \[out\]  
傳回時，包含指定資源為所需狀態之 **MSFT_ResourceInDesiredState** 類別的內嵌執行個體。

*ResourcesNotInDesiredState* \[out\]  
傳回時，包含指定資源不為所需狀態之 **MSFT_ResourceNotInDesiredState** 類別的內嵌執行個體。

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


