---
title: 在 Outlook 配置文件中检测 Exchange Server 版本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e2d8d8a9-7e8f-9cf0-56a8-d8a6281ad589
description: 上次修改时间:03 月3日, 2012
ms.openlocfilehash: c6aaac128e1a3e1a8d77d3fa8b6c50a335348b71
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424446"
---
# <a name="detect-the-version-of-exchange-server-in-an-outlook-profile"></a>在 Outlook 配置文件中检测 Exchange Server 版本

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含 c + + 中的代码示例, 演示如何使用**[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** 属性和**[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)** 属性获取 Microsoft Exchange SERVER 的版本信息。活动帐户已连接到。 
  
代码`GetProfileServiceVersion`示例中的函数接受一个配置文件作为输入参数。 根据**PR_PROFILE_SERVER_VERSION**属性和**PR_PROFILE_SERVER_FULL_VERSION**属性在给定的配置文件中是否存在, 该函数将获取每个属性, 并以输出的形式返回适当的版本信息。实参. 
  
`GetProfileServiceVersion`首先调用**[MAPIAdminProfiles](mapiadminprofiles.md)** 函数来创建配置文件管理对象。 然后, 它使用配置文件管理对象调用**[IProfAdmin:: AdminServices](iprofadmin-adminservices.md)** 以获取邮件服务管理对象。 使用邮件服务管理对象, 它调用**[IMsgServiceAdmin:: OpenProfileSection](imsgserviceadmin-openprofilesection.md)** 获取当前配置文件的一部分, 然后调用**[HrGetOneProp](hrgetoneprop.md)** 以验证这两个属性中的每个属性是否都存在于配置文件, 如果是, 则在相应的输出参数中设置版本信息。 
  
```cpp
TZDEFINITION* BinToTZDEFINITION(ULONG cbDef, LPBYTE lpbDef) 
{ 
    if (!lpbDef) return NULL; 
 
    // Update this if parsing code is changed. 
    // This checks the size up to the flag member. 
    if (cbDef &lt; 2*sizeof(BYTE) + 2*sizeof(WORD)) return NULL; 
 
    TZDEFINITION tzDef = {0}; 
    TZRULE* lpRules = NULL; 
    LPBYTE lpPtr = lpbDef; 
    WORD cchKeyName = NULL; 
    WCHAR* szKeyName = NULL; 
    WORD i = 0; 
 
    BYTE bMajorVersion = *((BYTE*)lpPtr); 
    lpPtr += sizeof(BYTE); 
    BYTE bMinorVersion = *((BYTE*)lpPtr); 
    lpPtr += sizeof(BYTE); 
 
    // We only understand TZ_BIN_VERSION_MAJOR 
    if (TZ_BIN_VERSION_MAJOR != bMajorVersion) return NULL; 
 
    // We only understand if &gt;= TZ_BIN_VERSION_MINOR 
    if (TZ_BIN_VERSION_MINOR &gt; bMinorVersion) return NULL; 
 
    lpPtr += sizeof(WORD); 
 
    tzDef.wFlags = *((WORD*)lpPtr); 
    lpPtr += sizeof(WORD); 
 
    if (TZDEFINITION_FLAG_VALID_GUID &amp; tzDef.wFlags) 
    { 
        if (lpbDef + cbDef - lpPtr &lt; sizeof(GUID)) return NULL; 
        tzDef.guidTZID = *((GUID*)lpPtr); 
        lpPtr += sizeof(GUID); 
    } 
 
    if (TZDEFINITION_FLAG_VALID_KEYNAME &amp; tzDef.wFlags) 
    { 
        if (lpbDef + cbDef - lpPtr &lt; sizeof(WORD)) return NULL; 
        cchKeyName = *((WORD*)lpPtr); 
        lpPtr += sizeof(WORD); 
        if (cchKeyName) 
        { 
            if (lpbDef + cbDef - lpPtr &lt; (BYTE)sizeof(WORD)*cchKeyName) return NULL; 
            szKeyName = (WCHAR*)lpPtr; 
            lpPtr += cchKeyName*sizeof(WORD); 
        } 
    } 
 
    if (lpbDef+ cbDef - lpPtr &lt; sizeof(WORD)) return NULL; 
    tzDef.cRules = *((WORD*)lpPtr); 
    lpPtr += sizeof(WORD); 
    if (tzDef.cRules) 
    { 
        lpRules = new TZRULE[tzDef.cRules]; 
        if (!lpRules) return NULL; 
 
        LPBYTE lpNextRule = lpPtr; 
        BOOL bRuleOK = false; 

```


