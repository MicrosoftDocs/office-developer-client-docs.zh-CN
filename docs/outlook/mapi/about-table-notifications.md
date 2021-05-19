---
title: 关于表通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00c9c6c2-fc21-4b9c-91fa-629450a22d37
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9a42ed1e196e8ac498ab5889b4419ff407db4748
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417950"
---
# <a name="about-table-notifications"></a>关于表通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端通常依赖表通知来了解对对象的更改，而不是注册以直接从对象接收通知。 导致发送通知的典型更改包括添加、删除或修改行以及任何关键错误。 通知到达后，客户端可以确定是否进行其他调用以重新加载表。 
  
由于表通知是异步的，因此存在一些问题，这些问题会使处理通知不如简单：
  
- 在数据 [TABLE_NOTIFICATION中传递](table_notification.md) 的数据可能并不代表表的最近状态。 例如，客户端可能会更改邮件，然后决定将其删除。 实现包含邮件的内容表的邮件存储提供程序发送两个通知：一个 TABLE_ROW_MODIFIED 事件，后跟一个 TABLE_ROW_DELETED 事件。 根据邮件存储提供程序通知时间，客户端在删除行TABLE_ROW_MODIFIED可能会收到通知。 
    
- 通知中包含的列集可能不同于表的当前列集。 MAPI 要求通知列集与生成通知时生效的列集匹配。 由于客户端可能随时（包括通知后）调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 来更改列集，因此这两个列集可能不会同步。 
    
- 仅对属于视图的行发送表通知。 也就是说，如果由于限制或表为折叠状态而从视图中排除行，则该行更改时不会发送通知。 此外，不会发送通知来通知客户端类别状态的变化。
    
客户端应注意，并非所有表都支持TABLE_SORT_DONE通知，并且应准备通过以下操作来处理此情况：
  
1. 强制排序为同步。
    
2. 当 [IMAPITable：：SortTable 返回时重新加载表的](imapitable-sorttable.md) 行。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

