---
title: 关于限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e119fa20-08b8-4c8d-93fc-56037220890d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d7294527fcd557ae2d4824b9a3215ff464f62c2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774476"
---
# <a name="about-restrictions"></a>关于限制

  
  
**适用于**： Outlook 
  
限制是一种方法来限制为仅与特定条件匹配的列的值这些行视图中的行数。 有许多不同的机会，使用的表的限制。 客户端应用程序可用于限制，例如，筛选搜索行的不支持属性，或具有属性设置为特定值，或查找内的重复收件人由特定人员，发送的邮件内容表消息。 
  
[IMAPITable::Restrict](imapitable-restrict.md)和[IMAPITable::FindRow](imapitable-findrow.md)方法用于设置对表格的限制。 **限制**对表格中应用此限制，而不检索任何行。 若要检索满足限制的行，则需要后续调用[IMAPITable::QueryRows](imapitable-queryrows.md)或类似的方法。 **FindRow**应用此限制，并检索与条件匹配的表中的第一行。 **FindRow**应用临时限制，这是中存在仅用于呼叫的持续时间，而**Restrict**应用更永久限制。 
  
某些客户端可以构建限制使用当前列中不包含的列。 支持这样的限制是可选的支持它的表实施添加值，特别是对于内容表。 不支持的表实施可以从**Restrict**呼叫或从**FindRow**呼叫 MAPI_E_NOT_FOUND 值返回 MAPI_E_TOO_COMPLEX 值。 
  
客户端应注意，即使不在当前的列组列上提供程序支持的限制，他们将得到更好的总体性能，通过指定他们想要在其限制与[IMAPITable::SetColumns](imapitable-setcolumns.md)中使用的列.
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

