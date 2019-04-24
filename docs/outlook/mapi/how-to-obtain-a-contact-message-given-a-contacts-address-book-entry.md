---
title: 在给定联系人通讯簿条目的情况中获取联系人邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a263894b-b3da-f1e4-a7da-ca3695bddc94
description: '上次修改时间: 2013 年8月13日'
ms.openlocfilehash: be988a3036c2d882f65e2e588cc9a40bfda146a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345953"
---
# <a name="obtain-a-contact-message-given-a-contacts-address-book-entry"></a>在给定联系人通讯簿条目的情况中获取联系人邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含一个 c + + `HrOpenContact`中的示例, 该示例演示如何使用标识联系人通讯簿中的条目的[CONTAB_ENTRYID](contab_entryid.md)结构来获取关联的 MAPI 联系人邮件。 
  
`HrOpenContact`具有以下参数: 
  
-  *lpSession*是表示当前会话的输入参数。 **LPMAPISESSION**在 MAPI 头文件 mapix 中定义为指向[IMAPISession: IUnknown](imapisessioniunknown.md)的指针。
    
-  *cbEntryID*是一个输入参数, 表示与*lpEntryID*关联的条目标识符的大小。 
    
-  *lpEntryID*是一个输入参数, 表示指向联系人通讯簿中条目的条目标识符的指针。 
    
-  *ulFlags*是一个输入参数, 表示包含 MAPI 联系人消息的对象访问标志的位掩码。 
    
-  *lpContactMessage*是一个输出参数, 表示指向 MAPI 联系人消息的指针。 
    
若要打开基础 MAPI 联系人消息, `HrOpenContact`请首先将*lpEntryID*转换为指向**CONTAB_ENTRYID**的指针。 然后, 它调用[IMAPISession:: OpenEntry](imapisession-openentry.md)以获取 MAPI 联系人消息, 将联系人通讯簿中的条目的*cbeid*和*abeid*字段作为参数进行传递, 该条目将分别标识条目标识符的大小和MAPI 联系人邮件的条目标识符。 
  
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

## <a name="see-also"></a>另请参阅

- [IMAPISession::OpenEntry](imapisession-openentry.md)

