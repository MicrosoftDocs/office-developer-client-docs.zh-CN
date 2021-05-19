---
title: 关于限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e119fa20-08b8-4c8d-93fc-56037220890d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 139526937380273703a96f91f2bae02a79debc76
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433106"
---
# <a name="about-restrictions"></a>关于限制

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
限制是一种将视图中的行数限制为仅具有与特定条件匹配的列值的行的方法。 对表使用限制有许多不同的机会。 例如，客户端应用程序可以使用限制来筛选特定人员发送的邮件的内容表，搜索不支持属性或将属性设置为特定值的行，或在邮件中查找重复的收件人。 
  
[IMAPITable：：Restrict](imapitable-restrict.md)和[IMAPITable：：FindRow](imapitable-findrow.md)方法用于对表设置限制。 **Restrict** 将限制应用于表，而不检索任何行。 若要仅检索满足限制的行，需要后续调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 或类似方法。 **FindRow** 应用限制并检索表中匹配条件的第一行。 **FindRow** 应用临时限制，此限制仅在调用期间存在， **而 Restrict** 应用更永久的限制。 
  
某些客户端可以使用当前列集外列构建限制。 支持此类限制是可选的，并且支持此限制的表实施者会增加值，特别是对于内容表。 不支持它的表实现程序可以从 Restrict MAPI_E_TOO_COMPLEX **返回** 值，也可以从 **FindRow** MAPI_E_NOT_FOUND返回值。 
  
客户端应注意，即使提供程序支持对不在当前列集的列的限制，它们也会通过指定他们在 [与 IMAPITable：：SetColumns](imapitable-setcolumns.md)的限制中打算使用的列，获得更好的整体性能。
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

