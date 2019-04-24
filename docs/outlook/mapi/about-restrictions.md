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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322118"
---
# <a name="about-restrictions"></a>关于限制

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
限制是一种将视图中的行数限制为仅包含与特定条件匹配的列的行数的方法。 对表格使用限制有许多不同的机会。 例如, 客户端应用程序可以使用限制来筛选由特定人员发送的邮件的内容表, 以搜索不支持属性或已将属性设置为特定值的行, 或查找中的重复收件人消息。 
  
[IMAPITable:: Restrict](imapitable-restrict.md)和[IMAPITable:: FindRow](imapitable-findrow.md)方法用于设置对表的限制。 **限制**对表应用限制, 而不检索任何行。 若要仅检索那些符合限制的行, 则需要对[IMAPITable:: QueryRows](imapitable-queryrows.md)或类似的方法进行后续调用。 **FindRow**应用限制, 并检索表中与条件匹配的第一行。 **FindRow**应用临时限制, 这仅在呼叫期间存在, 而**限制**应用更永久的限制。 
  
某些客户端可以使用不在当前列集中的列生成限制。 支持这种限制是可选的, 并且支持它的表实施者添加值, 尤其是对于内容表。 不支持它的表实施者可以从**FindRow**调用中返回**限制**调用或 MAPI_E_NOT_FOUND 值中的 MAPI_E_TOO_COMPLEX 值。 
  
客户端应注意, 即使提供程序对不在当前列集中的列支持限制, 它们也会获得更好的性能, 具体方法是通过在其对[IMAPITable:: SetColumns](imapitable-setcolumns.md)的限制中指定要使用的列来获得更好的性能。.
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

