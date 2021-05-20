---
title: 处理命名属性错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f56c56d8-db46-4c69-876f-2bbb4a5c1185
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 98b6adbc3a31994768a78b389e16eb3a6ece34bd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429864"
---
# <a name="handling-named-property-errors"></a><span data-ttu-id="6e286-103">处理命名属性错误</span><span class="sxs-lookup"><span data-stu-id="6e286-103">Handling named property errors</span></span>
  
<span data-ttu-id="6e286-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e286-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e286-105">当对实现者处理过大的 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 或 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 提出请求时，将返回错误值 MAPI_E_TOO_BIG。</span><span class="sxs-lookup"><span data-stu-id="6e286-105">When a request is made to [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) or [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) that is too large for the implementer to handle, the error value MAPI_E_TOO_BIG is returned.</span></span> <span data-ttu-id="6e286-106">调用方必须将他们的请求划分为多个请求，在一个循环中调用适当的方法。</span><span class="sxs-lookup"><span data-stu-id="6e286-106">Callers must divide their request into several requests, calling the appropriate method in a loop.</span></span> 
  
<span data-ttu-id="6e286-107">当调用导致部分成功时（例如，当请求针对映射到特定标识符的名称且找不到一个或多个名称时）时 **，GetNamesFromIDs** 将返回 MAPI_W_ERRORS_RETURNED，并且将 PT_ERROR 在属性标记数组中缺少的属性的属性类型中。</span><span class="sxs-lookup"><span data-stu-id="6e286-107">When a call results in partial success, such as when the request is for names that map to specific identifiers and one or more names cannot be found, **GetNamesFromIDs** returns MAPI_W_ERRORS_RETURNED and places PT_ERROR in the property type for the missing property in the property tag array.</span></span> 
  
<span data-ttu-id="6e286-108">有时，客户端调用 **GetNamesFromIDs，** 这样不会返回任何属性，例如，当指定的属性集没有属性时，或者当所有命名属性的类型都由标志排除时。</span><span class="sxs-lookup"><span data-stu-id="6e286-108">Sometimes a client makes a call to **GetNamesFromIDs** that results in no properties being returned, such as when there are no properties in a specified property set, or when all named properties are of a type excluded by the flags.</span></span> <span data-ttu-id="6e286-109">客户端可以期望服务提供商：</span><span class="sxs-lookup"><span data-stu-id="6e286-109">Clients can expect service providers to:</span></span> 
  
- <span data-ttu-id="6e286-110">返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="6e286-110">Return S_OK.</span></span>
    
- <span data-ttu-id="6e286-111">将属性标记数组指针的内容设置为新分配的属性标记数组，其 **cValues** 成员集为零。</span><span class="sxs-lookup"><span data-stu-id="6e286-111">Set the contents of the property tag array pointer to a newly allocated property tag array with its **cValues** member set to zero.</span></span> 
    
- <span data-ttu-id="6e286-112">将 [MAPINAMEID](mapinameid.md) 结构数组的内容设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6e286-112">Set the contents of the [MAPINAMEID](mapinameid.md) structure array to NULL.</span></span> 
    
- <span data-ttu-id="6e286-113">将 **MAPINAMEID** 结构计数的内容设置为零。</span><span class="sxs-lookup"><span data-stu-id="6e286-113">Set the contents of the count of **MAPINAMEID** structures to zero.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6e286-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e286-114">See also</span></span>

- [<span data-ttu-id="6e286-115">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="6e286-115">MAPI Named Properties</span></span>](mapi-named-properties.md)

