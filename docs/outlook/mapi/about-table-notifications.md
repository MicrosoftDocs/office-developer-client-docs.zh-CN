---
title: 关于表格通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00c9c6c2-fc21-4b9c-91fa-629450a22d37
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9a42ed1e196e8ac498ab5889b4419ff407db4748
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321838"
---
# <a name="about-table-notifications"></a>关于表格通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端通常依靠表通知来了解对对象的更改, 而不是注册以直接从对象接收通知。 导致发送通知的典型更改包括添加、删除或修改行和任何严重错误。 当通知到达时, 客户端可以确定是否执行另一个调用来重新加载表。 
  
由于表通知是异步的, 因此有几个问题会导致处理通知不是很简单:
  
- [TABLE_NOTIFICATION](table_notification.md)结构中传递的数据可能不表示表的最新状态。 例如, 客户端可能会对邮件进行更改, 然后决定将其删除。 实现包含邮件的内容表格的邮件存储提供程序发送两个通知: 一个 TABLE_ROW_MODIFIED 事件, 后跟 TABLE_ROW_DELETED 事件。 根据邮件存储提供程序时间通知的方式, 客户端可能会在删除行后收到 TABLE_ROW_MODIFIED 通知。 
    
- 通知附带的列集可能与表的当前列集不同。 MAPI 要求通知列设置与生成通知时有效的列集相匹配。 由于客户端可以调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)以随时更改列集 (包括在通知之后), 因此两列集可能不会同步。 
    
- 仅对作为视图一部分的行发送表通知。 也就是说, 如果由于限制而从视图中排除某行, 或者表处于折叠状态, 则在该行发生更改时不会发送任何通知。 此外, 不会发送任何通知, 以通知客户端有关类别状态的更改。
    
客户端应注意, 并非所有表都支持 TABLE_SORT_DONE 通知, 应通过以下方式准备处理此条件:
  
1. 强制进行排序以进行同步。
    
2. 在[IMAPITable:: SortTable](imapitable-sorttable.md)返回时重新加载表的行。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

