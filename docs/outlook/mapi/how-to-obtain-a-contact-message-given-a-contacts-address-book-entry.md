---
title: 获取给定联系人通讯簿条目联系人邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a263894b-b3da-f1e4-a7da-ca3695bddc94
description: 上次修改时间： 2013 年 8 月 13 日
ms.openlocfilehash: 346e6bc471f5257aacb34c2e7d02a0aade1bb46e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775110"
---
# <a name="obtain-a-contact-message-given-a-contacts-address-book-entry"></a>获取给定联系人通讯簿条目联系人邮件

**适用于**： Outlook 
  
本主题包含在 c + +，示例`HrOpenContact`，显示如何使用标识获取关联的 MAPI 联系人邮件联系人通讯簿中的条目的[CONTAB_ENTRYID](contab_entryid.md)结构。 
  
`HrOpenContact`具有以下参数： 
  
-  *lpSession*为输入的参数表示当前会话。 **LPMAPISESSION** MAPI 头文件 mapix.h 中定义为一个指向[IMAPISession: IUnknown](imapisessioniunknown.md)。
    
-  *cbEntryID*为输入的参数表示与*lpEntryID*关联的项标识符的大小。 
    
-  *lpEntryID*为输入的参数表示指向联系人通讯簿中的条目的项标识符。 
    
-  *ulFlags*为输入的参数表示包含到 MAPI 联系人邮件对象访问标志位掩码。 
    
-  *lpContactMessage*是表示指向到 MAPI 联系人邮件输出参数。 
    
若要打开基础的 MAPI 联系人邮件，`HrOpenContact`首先将强制转换为**CONTAB_ENTRYID**指针*lpEntryID* 。 然后，它调用[IMAPISession::OpenEntry](imapisession-openentry.md)获取 MAPI 联系人邮件中，将作为参数传递联系人通讯簿中的条目标识分别的项标识符的大小的*cbeid*和*abeid*字段和MAPI 联系人消息的项标识符。 
  
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

