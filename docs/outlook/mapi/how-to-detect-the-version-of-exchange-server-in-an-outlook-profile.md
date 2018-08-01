---
title: Outlook 配置文件中检测 Exchange Server 的版本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e2d8d8a9-7e8f-9cf0-56a8-d8a6281ad589
description: 上次修改时间： 2012 年 7 月 3 日
ms.openlocfilehash: 3ed3def3fd76ec4f67239958b5d5164d97f81d8d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775087"
---
# <a name="detect-the-version-of-exchange-server-in-an-outlook-profile"></a><span data-ttu-id="0faa7-103">Outlook 配置文件中检测 Exchange Server 的版本</span><span class="sxs-lookup"><span data-stu-id="0faa7-103">Detect the version of Exchange Server in an Outlook profile</span></span>

<span data-ttu-id="0faa7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0faa7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0faa7-105">本主题演示如何使用**[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** 属性和**[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)** 属性来获取活动帐户是在 Microsoft Exchange Server 版本信息的 c + + 中包含的代码示例连接到。</span><span class="sxs-lookup"><span data-stu-id="0faa7-105">This topic includes a code sample in C++ that shows how to use the **[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** property and **[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)** property to obtain version information of the Microsoft Exchange Server that the active account is connected to.</span></span> 
  
<span data-ttu-id="0faa7-106">`GetProfileServiceVersion`函数中的代码示例接受一个配置文件作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="0faa7-106">The  `GetProfileServiceVersion` function in the code sample accepts a profile as an input parameter.</span></span> <span data-ttu-id="0faa7-107">根据是否**PR_PROFILE_SERVER_VERSION**属性和**PR_PROFILE_SERVER_FULL_VERSION**属性中存在的给定配置文件，该函数获取每个属性，并返回作为输出的适当版本信息参数。</span><span class="sxs-lookup"><span data-stu-id="0faa7-107">Depending on whether the **PR_PROFILE_SERVER_VERSION** property and the **PR_PROFILE_SERVER_FULL_VERSION** property exist in the given profile, the function gets each property and returns the appropriate version information as output parameters.</span></span> 
  
<span data-ttu-id="0faa7-108">`GetProfileServiceVersion`首先调用**[MAPIAdminProfiles](mapiadminprofiles.md)** 函数以创建配置文件管理对象。</span><span class="sxs-lookup"><span data-stu-id="0faa7-108">`GetProfileServiceVersion` first calls the **[MAPIAdminProfiles](mapiadminprofiles.md)** function to create a profile administration object.</span></span> <span data-ttu-id="0faa7-109">然后使用配置文件管理对象调用**[IProfAdmin::AdminServices](iprofadmin-adminservices.md)** 获取消息服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="0faa7-109">It then uses the profile administration object to call **[IProfAdmin::AdminServices](iprofadmin-adminservices.md)** to obtain a message service administration object.</span></span> <span data-ttu-id="0faa7-110">使用邮件服务管理对象，它调用**[IMsgServiceAdmin::OpenProfileSection](imsgserviceadmin-openprofilesection.md)** 获取当前配置文件的一部分，然后调用**[HrGetOneProp](hrgetoneprop.md)** 以验证是否每两个属性的那一节中存在配置文件，并如果是这样，在相应的输出参数中设置的版本信息。</span><span class="sxs-lookup"><span data-stu-id="0faa7-110">Using the message service administration object, it calls **[IMsgServiceAdmin::OpenProfileSection](imsgserviceadmin-openprofilesection.md)** to obtain a section of the current profile, and then calls **[HrGetOneProp](hrgetoneprop.md)** to verify if each of the two properties exists in that section of the profile, and if so, sets the version information in the appropriate output parameters.</span></span> 
  
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


