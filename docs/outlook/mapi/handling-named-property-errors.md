---
title: 处理名为属性错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f56c56d8-db46-4c69-876f-2bbb4a5c1185
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f6c12973a3ee2f9842e74f6f01b94553659dc1ad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583307"
---
# <a name="handling-named-property-errors"></a><span data-ttu-id="4faad-103">处理名为属性错误</span><span class="sxs-lookup"><span data-stu-id="4faad-103">Handling named property errors</span></span>
  
<span data-ttu-id="4faad-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4faad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4faad-105">当[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)或[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)太大的实施者处理的请求时，则返回错误值为 MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="4faad-105">When a request is made to [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) or [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) that is too large for the implementer to handle, the error value MAPI_E_TOO_BIG is returned.</span></span> <span data-ttu-id="4faad-106">呼叫者必须将其请求分为几个请求循环调用相应的方法。</span><span class="sxs-lookup"><span data-stu-id="4faad-106">Callers must divide their request into several requests, calling the appropriate method in a loop.</span></span> 
  
<span data-ttu-id="4faad-107">时找不到导致部分成功，如请求时将映射到特定的标识符的名称和一个或多个名称之间的呼叫， **GetNamesFromIDs**返回 MAPI_W_ERRORS_RETURNED，并将 PT_ERROR 属性类型放缺少该属性标记数组中的属性。</span><span class="sxs-lookup"><span data-stu-id="4faad-107">When a call results in partial success, such as when the request is for names that map to specific identifiers and one or more names cannot be found, **GetNamesFromIDs** returns MAPI_W_ERRORS_RETURNED and places PT_ERROR in the property type for the missing property in the property tag array.</span></span> 
  
<span data-ttu-id="4faad-108">有时，客户端到结果中要返回，例如没有属性的**GetNamesFromIDs**调用中指定的属性集，没有任何属性或由标志排除类型的所有命名的属性时。</span><span class="sxs-lookup"><span data-stu-id="4faad-108">Sometimes a client makes a call to **GetNamesFromIDs** that results in no properties being returned, such as when there are no properties in a specified property set, or when all named properties are of a type excluded by the flags.</span></span> <span data-ttu-id="4faad-109">客户端可以预期到服务提供商：</span><span class="sxs-lookup"><span data-stu-id="4faad-109">Clients can expect service providers to:</span></span> 
  
- <span data-ttu-id="4faad-110">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4faad-110">Return S_OK.</span></span>
    
- <span data-ttu-id="4faad-111">设置为新分配的属性标记数组与它设置为零的**cValues**成员属性标记数组指针的内容。</span><span class="sxs-lookup"><span data-stu-id="4faad-111">Set the contents of the property tag array pointer to a newly allocated property tag array with its **cValues** member set to zero.</span></span> 
    
- <span data-ttu-id="4faad-112">设置为 NULL [MAPINAMEID](mapinameid.md)结构数组的内容。</span><span class="sxs-lookup"><span data-stu-id="4faad-112">Set the contents of the [MAPINAMEID](mapinameid.md) structure array to NULL.</span></span> 
    
- <span data-ttu-id="4faad-113">设置的计数**MAPINAMEID**结构为零的内容。</span><span class="sxs-lookup"><span data-stu-id="4faad-113">Set the contents of the count of **MAPINAMEID** structures to zero.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="4faad-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4faad-114">See also</span></span>

- [<span data-ttu-id="4faad-115">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="4faad-115">MAPI Named Properties</span></span>](mapi-named-properties.md)

