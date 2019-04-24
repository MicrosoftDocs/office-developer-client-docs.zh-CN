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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299368"
---
# <a name="handling-named-property-errors"></a>处理命名属性错误
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当对[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)或[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)发出的请求对要处理的实施者来说太大时, 将返回错误值 MAPI_E_TOO_BIG。 呼叫者必须将其请求划分为多个请求, 并在循环中调用适当的方法。 
  
当呼叫导致部分成功时, 例如, 当请求用于映射到特定标识符的名称时, 如果找不到一个或多个名称, 则**GetNamesFromIDs**将返回 MAPI_W_ERRORS_RETURNED, 并将 PT_ERROR 放在属性类型中, 以获取缺少的属性在属性标记数组中。 
  
有时, 客户端调用**GetNamesFromIDs** , 从而导致不会返回任何属性, 例如在指定的属性集中没有任何属性时, 或者当所有命名属性的类型被标志排除时。 客户端可以期望服务提供商执行以下操作: 
  
- 返回 S_OK。
    
- 将属性标记数组指针的内容设置为其**cValues**成员设置为零的新分配的属性标记数组。 
    
- 将[MAPINAMEID](mapinameid.md)结构数组的内容设置为 NULL。 
    
- 将**MAPINAMEID**结构的计数的内容设置为零。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 命名属性](mapi-named-properties.md)

