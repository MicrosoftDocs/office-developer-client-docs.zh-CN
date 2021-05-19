---
title: 对条目 ID 和附件 ID 进行编码的算法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: b9ae6679-99b7-6509-74d4-12aa13d54928
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c39fe513be122f265fdc316629a3e64a156fdc1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420134"
---
# <a name="algorithm-to-encode-entry-ids-and-attachment-ids"></a>对条目 ID 和附件 ID 进行编码的算法

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
存储提供程序可以将条目 ID 和附件 ID 作为 MAPI 统一资源定位器 (URL) 的一部分发送到 MAPI 协议处理程序，以标识已准备好编制索引的对象。 存储提供程序将条目 ID 和附件 ID 编码为 Unicode 字符串。 本主题介绍一种算法，该算法可生成条目 ID 或附件 ID 的精简表示形式。
  
```cpp
const WORD kwBaseOffset = 0xAC00;  // Hangul char range (AC00-D7AF) 
LPWSTR EncodeID(ULONG cbEID, LPENTRYID rgbID) 
{ 
    ULONG   i = 0; 
    LPWSTR  pwzDst = NULL; 
    LPBYTE  pbSrc = NULL; 
    LPWSTR  pwzIDEncoded = NULL; 
 
    // rgbID is the item Entry ID or the attachment ID 
    // cbID is the size in bytes of rgbID 
 
    // Allocate memory for pwzIDEncoded 
    pwzIDEncoded = new WCHAR[cbEID]; 
    if (!pwzIDEncoded) return NULL; 
 
    for (i = 0, pbSrc = (LPBYTE)rgbID, pwzDst = pwzIDEncoded; 
        i < cbEID; 
        i++, pbSrc++, pwzDst++) 
    { 
        *pwzDst = (WCHAR) (*pbSrc + kwBaseOffset); 
    } 
 
    // Ensure NULL terminated 
    *pwzDst = L'\0'; 
 
    // pwzIDEncoded now contains the entry ID encoded. 
    return pwzIDEncoded; 
}
```

## <a name="see-also"></a>另请参阅



[关于Notification-Based存储索引](about-notification-based-store-indexing.md)
  
[关于用于索引Notification-Based MAPI URL](about-mapi-urls-for-notification-based-indexing.md)

