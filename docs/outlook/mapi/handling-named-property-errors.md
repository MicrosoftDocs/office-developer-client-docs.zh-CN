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
# <a name="handling-named-property-errors"></a>处理命名属性错误
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当对实现者处理过大的 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 或 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 提出请求时，将返回错误值 MAPI_E_TOO_BIG。 调用方必须将他们的请求划分为多个请求，在一个循环中调用适当的方法。 
  
当调用导致部分成功时（例如，当请求针对映射到特定标识符的名称且找不到一个或多个名称时）时 **，GetNamesFromIDs** 将返回 MAPI_W_ERRORS_RETURNED，并且将 PT_ERROR 在属性标记数组中缺少的属性的属性类型中。 
  
有时，客户端调用 **GetNamesFromIDs，** 这样不会返回任何属性，例如，当指定的属性集没有属性时，或者当所有命名属性的类型都由标志排除时。 客户端可以期望服务提供商： 
  
- 返回S_OK。
    
- 将属性标记数组指针的内容设置为新分配的属性标记数组，其 **cValues** 成员集为零。 
    
- 将 [MAPINAMEID](mapinameid.md) 结构数组的内容设置为 NULL。 
    
- 将 **MAPINAMEID** 结构计数的内容设置为零。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 命名属性](mapi-named-properties.md)

