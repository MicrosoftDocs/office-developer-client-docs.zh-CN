---
title: 编码条目 Id 和附件 Id 的算法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: b9ae6679-99b7-6509-74d4-12aa13d54928
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 710ba5173dcce6e948e1f49c7d82e46bc83b8200
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774546"
---
# <a name="algorithm-to-encode-entry-ids-and-attachment-ids"></a><span data-ttu-id="b88c2-103">编码条目 Id 和附件 Id 的算法</span><span class="sxs-lookup"><span data-stu-id="b88c2-103">Algorithm to Encode Entry IDs and Attachment IDs</span></span>

  
  
<span data-ttu-id="b88c2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b88c2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b88c2-105">存储提供程序可以发送一部分的 MAPI 统一资源定位器 (URL) 的条目 ID 和附件 ID 到 MAPI 协议处理程序，以确定已准备好进行索引的对象。</span><span class="sxs-lookup"><span data-stu-id="b88c2-105">A store provider can send as part of a MAPI Uniform Resource Locator (URL) an entry ID and an attachment ID to the MAPI Protocol Handler to identify an object that is ready for indexing.</span></span> <span data-ttu-id="b88c2-106">存储提供程序将条目 ID 和附件 ID 编码为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="b88c2-106">The store provider encodes the entry ID and attachment ID as Unicode strings.</span></span> <span data-ttu-id="b88c2-107">本主题演示生成的条目 ID 或附件 id。 紧凑形式表示的算法</span><span class="sxs-lookup"><span data-stu-id="b88c2-107">This topic shows an algorithm that generates a compact representation of the entry ID or attachment ID.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="b88c2-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b88c2-108">See also</span></span>



[<span data-ttu-id="b88c2-109">有关基于通知存储索引</span><span class="sxs-lookup"><span data-stu-id="b88c2-109">About Notification-Based Store Indexing</span></span>](about-notification-based-store-indexing.md)
  
[<span data-ttu-id="b88c2-110">有关基于通知的索引的 MAPI Url</span><span class="sxs-lookup"><span data-stu-id="b88c2-110">About MAPI URLs for Notification-Based Indexing</span></span>](about-mapi-urls-for-notification-based-indexing.md)

