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
# <a name="obtain-a-contact-message-given-a-contacts-address-book-entry"></a><span data-ttu-id="c9aef-103">获取给定联系人通讯簿条目联系人邮件</span><span class="sxs-lookup"><span data-stu-id="c9aef-103">Obtain a contact message given a contacts address book entry</span></span>

<span data-ttu-id="c9aef-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c9aef-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c9aef-105">本主题包含在 c + +，示例`HrOpenContact`，显示如何使用标识获取关联的 MAPI 联系人邮件联系人通讯簿中的条目的[CONTAB_ENTRYID](contab_entryid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c9aef-105">This topic contains an example in C++, `HrOpenContact`, that shows how to use the [CONTAB_ENTRYID](contab_entryid.md) structure that identifies an entry in a Contacts Address Book to obtain the associated MAPI Contact message.</span></span> 
  
<span data-ttu-id="c9aef-106">`HrOpenContact`具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="c9aef-106">`HrOpenContact` has the following parameters:</span></span> 
  
-  <span data-ttu-id="c9aef-107">*lpSession*为输入的参数表示当前会话。</span><span class="sxs-lookup"><span data-stu-id="c9aef-107">*lpSession*  is an input parameter representing the current session.</span></span> <span data-ttu-id="c9aef-108">**LPMAPISESSION** MAPI 头文件 mapix.h 中定义为一个指向[IMAPISession: IUnknown](imapisessioniunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="c9aef-108">**LPMAPISESSION** is defined in the MAPI header file mapix.h as a pointer to [IMAPISession : IUnknown](imapisessioniunknown.md).</span></span>
    
-  <span data-ttu-id="c9aef-109">*cbEntryID*为输入的参数表示与*lpEntryID*关联的项标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="c9aef-109">*cbEntryID*  is an input parameter representing the size of the entry identifier associated with  *lpEntryID*  .</span></span> 
    
-  <span data-ttu-id="c9aef-110">*lpEntryID*为输入的参数表示指向联系人通讯簿中的条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="c9aef-110">*lpEntryID*  is an input parameter representing a pointer to the entry identifier of an entry in a Contact Address Book.</span></span> 
    
-  <span data-ttu-id="c9aef-111">*ulFlags*为输入的参数表示包含到 MAPI 联系人邮件对象访问标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="c9aef-111">*ulFlags*  is an input parameter representing a bitmask containing object access flags to the MAPI Contact message.</span></span> 
    
-  <span data-ttu-id="c9aef-112">*lpContactMessage*是表示指向到 MAPI 联系人邮件输出参数。</span><span class="sxs-lookup"><span data-stu-id="c9aef-112">*lpContactMessage*  is an output parameter representing a pointer to the MAPI Contact message.</span></span> 
    
<span data-ttu-id="c9aef-113">若要打开基础的 MAPI 联系人邮件，`HrOpenContact`首先将强制转换为**CONTAB_ENTRYID**指针*lpEntryID* 。</span><span class="sxs-lookup"><span data-stu-id="c9aef-113">To open the underlying MAPI Contact message,  `HrOpenContact` first casts  *lpEntryID*  to a pointer to **CONTAB_ENTRYID**.</span></span> <span data-ttu-id="c9aef-114">然后，它调用[IMAPISession::OpenEntry](imapisession-openentry.md)获取 MAPI 联系人邮件中，将作为参数传递联系人通讯簿中的条目标识分别的项标识符的大小的*cbeid*和*abeid*字段和MAPI 联系人消息的项标识符。</span><span class="sxs-lookup"><span data-stu-id="c9aef-114">It then calls [IMAPISession::OpenEntry](imapisession-openentry.md) to obtain the MAPI Contact message, passing as parameters the  *cbeid*  and  *abeid*  fields of the entry in the Contacts Address Book that identify respectively the size of the entry identifier and the entry identifier of the MAPI Contact message.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="c9aef-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9aef-115">See also</span></span>

- [<span data-ttu-id="c9aef-116">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="c9aef-116">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)

