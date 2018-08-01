---
title: 关于表通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00c9c6c2-fc21-4b9c-91fa-629450a22d37
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3dfc67c8bcd899396da5371c614fd221cd9b2251
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774475"
---
# <a name="about-table-notifications"></a>关于表通知

  
  
**适用于**： Outlook 
  
客户端通常依靠表通知，若要了解的而不是注册直接从对象接收通知的对象更改。 导致发送通知的典型更改包括添加、 删除或修改的行和任何错误。 当到达通知时，客户端可以确定是进行重新加载表的另一个呼叫。 
  
表通知是异步的因为有可以处理通知小于变得非常简单的几个问题：
  
- 传递[TABLE_NOTIFICATION](table_notification.md)结构中的数据不能表示表的最新状态。 例如，客户端可能更改了一条消息，然后确定可将其删除。 消息存储提供程序实现的内容表包含邮件的发送两个通知： TABLE_ROW_MODIFIED 事件后跟 TABLE_ROW_DELETED 事件。 如何消息存储提供程序时间通知，根据客户端可能会收到 TABLE_ROW_MODIFIED 通知后删除的行。 
    
- 设置包含在通知的列可能不同于表的当前列组。 MAPI 需要通知列组匹配列集已在生成通知的时间起作用。 因为可能为客户端调用[IMAPITable::SetColumns](imapitable-setcolumns.md)更改随时设置列 — 包括通知之后 — 可能不同步的两列集。 
    
- 表通知仅发送是视图的一部分的行。 即如果由于限制视图从排除行或表处于折叠状态，因此，如果该行更改将会不发送任何通知。 此外，不发送任何通知类别状态更改通知客户端。
    
客户端应请注意，不是所有表支持 TABLE_SORT_DONE 通知，应做好处理通过这种情况：
  
1. 强制要同步的排序。
    
2. [IMAPITable::SortTable](imapitable-sorttable.md)返回时，重新加载 table 的行。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

