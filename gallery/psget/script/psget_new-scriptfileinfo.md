---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,cmdlet,組件庫"
ms.date: 2016-10-14
contributor: manikb
title: psget_new scriptfileinfo
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: 8a534132c9622c699b636252e7c4bf7eafcf4d44

---

# New-ScriptFileInfo

建立含有中繼資料的指令檔。

## 描述

New-ScriptFileInfo Cmdlet 會建立 PowerShell 指令檔 (包括指令碼的中繼資料)。

## Cmdlet 語法

```powershell
Get-Command -Name New-ScriptFileInfo -Module PowerShellGet -Syntax
```

## Cmdlet 線上說明參考資料

[New-ScriptFileInfo](http://go.microsoft.com/fwlink/?LinkId=619792)

## 範例命令

### PassThru 參數

```powershell
New-ScriptFileInfo -Description "Script file description." -PassThru
```

### New-ScriptFileInfo Cmdlet
New-ScriptFileInfo Cmdlet 可讓您建立具中繼資料的新指令碼檔案，例如版本、GUID、作者和描述等等。 

```powershell
# Create a new script file with minimum required metadata values
New-ScriptFileInfo -Path C:\ScriptSharingDemo\Demo-Script.ps1 -Description "Script file description goes here"

Get-Content -Path C:\ScriptSharingDemo\Demo-Script.ps1
<#PSScriptInfo
.VERSION 1.0
.GUID 926b47c3-6af2-4b18-b6f5-8b813a9e93ab
.AUTHOR manikb
.COMPANYNAME
.COPYRIGHT
.TAGS
.LICENSEURI
.PROJECTURI
.ICONURI
.EXTERNALMODULEDEPENDENCIES
.REQUIREDSCRIPTS
.EXTERNALSCRIPTDEPENDENCIES
.RELEASENOTES
#>
<#
.DESCRIPTION
Script file description goes here
#>
Param()

# Validate and get the script metadata
Test-ScriptFileInfo -Path C:\ScriptSharingDemo\Demo-Script.ps1
Version Name Author Description
------- ---- ------ -----------
1.0 Demo-Script manikb Script file description goes here

# Add function and workflow to the script file
Add-Content -Path C:\ScriptSharingDemo\Demo-Script.ps1 -Value @"
   
    Function Demo-ScriptFunction { 'Demo-ScriptFunction' }
   
    Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }
   
    Demo-ScriptFunction
    Demo-ScriptWorkflow
"@

# Validate and get the script metadata
Test-ScriptFileInfo -Path C:\ScriptSharingDemo\Demo-Script.ps1

Version Name Author Description
------- ---- ------ -----------
1.0 Demo-Script manikb Script file description goes here

# Create a script file all metadata properties
New-ScriptFileInfo -Path 'C:\ScriptSharingDemo\Demo-ScriptWithCompletePSScriptInfo.ps1' `
    -Version 1.0 `
    -Author 'manikb' `
    -Description "my new script file" `
    -CompanyName "Microsoft Corporation" `
    -Copyright "(c) 2015 Microsoft Corporation. All rights reserved." `
    -Tags @('Tag1', 'Tag2', 'Tag3') `
    -ProjectUri 'https://contoso.com' `
    -LicenseUri "https://contoso.com/License" `
    -IconUri 'https://contoso.com/Icon' `
    -ReleaseNotes @('contoso script now supports following features',
    'Feature 1',
    'Feature 2',
    'Feature 3',
    'Feature 4',
    'Feature 5') `
    -RequiredModules @('RequiredModule1',
    @{ModuleName='RequiredModule2';ModuleVersion='1.0'},
    @{ModuleName='RequiredModule3';RequiredVersion='2.0'},
    @{ModuleName = 'RequiredModule4'; ModuleVersion = '0.1'; MaximumVersion = '1.*'; },
    @{ModuleName = 'RequiredModule5'; MaximumVersion = '1.*'; },
    'ExternalModule1') `
    -ExternalModuleDependencies 'ExternalModule1' `
    -RequiredScripts 'Start-WFContosoServer', 'Stop-ContosoServerScript', 'ExternalScript1' `
    -ExternalScriptDependencies 'ExternalScript1'

# Add function and workflow to the script file
Add-Content -Path 'C:\ScriptSharingDemo\Demo-ScriptWithCompletePSScriptInfo.ps1' -Value @"
   
    Function Demo-ScriptFunction { 'Demo-ScriptFunction' }
   
    Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }
   
    Demo-ScriptFunction
    Demo-ScriptWorkflow
"@

Get-Content -Path C:\ScriptSharingDemo\Demo-ScriptWithCompletePSScriptInfo.ps1

<#PSScriptInfo
.VERSION 1.0
.GUID fe4cc121-f87e-4ddb-8186-ff362e23a935
.AUTHOR manikb
.COMPANYNAME Microsoft Corporation
.COPYRIGHT (c) 2015 Microsoft Corporation. All rights reserved.
.TAGS Tag1 Tag2 Tag3
.LICENSEURI https://contoso.com/License
.PROJECTURI https://contoso.com/
.ICONURI https://contoso.com/Icon
.EXTERNALMODULEDEPENDENCIES ExternalModule1
.REQUIREDSCRIPTS Start-WFContosoServer,Stop-ContosoServerScript,ExternalScript1
.EXTERNALSCRIPTDEPENDENCIES ExternalScript1
.RELEASENOTES
contoso script now supports following features
Feature 1
Feature 2
Feature 3
Feature 4
Feature 5
#>
#Requires -Module RequiredModule1
#Requires -Module @{ModuleName = 'RequiredModule2'; ModuleVersion = '1.0'}
#Requires -Module @{RequiredVersion = '2.0'; ModuleName = 'RequiredModule3'}
#Requires -Module @{ModuleVersion = '0.1'; ModuleName = 'RequiredModule4'; MaximumVersion = '1.*'}
#Requires -Module @{MaximumVersion = '1.*'; ModuleName = 'RequiredModule5'}
#Requires -Module ExternalModule1
<#
.DESCRIPTION
my new script file
#>
Param()
Function Demo-ScriptFunction { 'Demo-ScriptFunction' }
Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }
Demo-ScriptFunction
Demo-ScriptWorkflow

# Validate and get the script metadata
Test-ScriptFileInfo C:\ScriptSharingDemo\Demo-ScriptWithCompletePSScriptInfo.ps1 | Format-List * -Force

Name : Demo-ScriptWithCompletePSScriptInfo
Version : 1.0
Guid : fe4cc121-f87e-4ddb-8186-ff362e23a935
Path : C:\ScriptSharingDemo\Demo-ScriptWithCompletePSScriptInfo.ps1
ScriptBase : C:\ScriptSharingDemo
Description : my new script file
Author : manikb
CompanyName : Microsoft Corporation
Copyright : (c) 2015 Microsoft Corporation. All rights reserved.
Tags : {Tag1, Tag2, Tag3}
ReleaseNotes : {contoso script now supports following features, Feature 1, Feature 2, Feature 3...}
RequiredModules : {RequiredModule1, @{ ModuleName = 'RequiredModule2'; ModuleVersion = '1.0' }, @{ ModuleName = 'RequiredModule3'; RequiredVersion = '2.0' }, @{ ModuleName = 'RequiredModule4'; ModuleVersion = '0.1';
MaximumVersion = '1.*' }...}
ExternalModuleDependencies : ExternalModule1
RequiredScripts : {Start-WFContosoServer, Stop-ContosoServerScript, ExternalScript1}
ExternalScriptDependencies : ExternalScript1
LicenseUri : https://contoso.com/License
ProjectUri : https://contoso.com/
IconUri : https://contoso.com/Icon
DefinedCommands : {Demo-ScriptFunction, Demo-ScriptWorkflow}
DefinedFunctions : Demo-ScriptFunction
DefinedWorkflows : Demo-ScriptWorkflow
```




<!--HONumber=Oct16_HO2-->


