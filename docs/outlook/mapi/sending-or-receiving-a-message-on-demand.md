---
title: 发送或接收按需型消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 479404c5-4926-402a-aa12-75dd23276d75
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ece5340497f83862b711f076c8c6346e14ec9355
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778744"
---
# <a name="sending-or-receiving-a-message-on-demand"></a>发送或接收按需型消息
  
**适用于**： Outlook 
  
客户端通常依靠 MAPI 子系统 — MAPI 后台处理程序和服务提供程序 — 处理的邮件传输和接收的时间。 但是，您可以通过使用 MAPI 后台处理程序或传输提供程序的状态对象修改此计时。
  
[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法从一个或多个传输提供程序的传入或传出队列中删除所有邮件。 下面的过程介绍两种技术可以发送或接收的消息的需求。 第一个过程使用 MAPI 后台处理程序的状态对象来刷新的配置文件; 中每个传输提供程序的队列第二个过程刷新单个传输提供程序的队列。 
  
### <a name="to-flush-all-incoming-or-outgoing-queues-in-a-single-operation"></a>刷新在单一操作中的所有传入或传出队列
  
1. 调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。 
    
2. 调用状态表[IMAPITable::SetColumns](imapitable-setcolumns.md)方法，以限制设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 的列。
    
3. 构建使用[SPropertyRestriction](spropertyrestriction.md)结构匹配**PR_RESOURCE_TYPE**与 MAPI_SPOOLER 属性限制。 
    
4. 呼叫[HrQueryAllRows](hrqueryallrows.md)，传递**SPropertyRestriction**结构中，若要检索的行代表 MAPI 后台处理程序的状态。 
    
5. 传递给[IMAPISession::OpenEntry](imapisession-openentry.md)打开 MAPI 后台处理程序的状态对象**PR_ENTRYID**列。 
    
6. 调用 MAPI 后台处理程序的[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法，传递 FLUSH_NO_UI 标志禁止在用户界面和 FLUSH_DOWNLOAD 或 FLUSH_UPLOAD 刷新传出或传入队列的标志。 
    
7. 释放状态对象和状态表，以及分配表的[SRowSet](srowset.md)结构。 
    
### <a name="to-flush-incoming-or-outgoing-queues-individually-by-transport-provider"></a>刷新分别由传输提供程序的传入或传出队列
  
1. 调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。 
    
2. 调用状态表[IMAPITable::SetColumns](imapitable-setcolumns.md)方法，以限制设置为**PR_ENTRYID**和**PR_RESOURCE_TYPE**的列。
    
3. 构建使用[SPropertyRestriction](spropertyrestriction.md)结构匹配**PR_RESOURCE_TYPE**与 MAPI_TRANSPORT_PROVIDER 属性限制。 
    
4. 调用[HrQueryAllRows](hrqueryallrows.md)，传递在**SPropertyRestriction**结构中，以检索由传输提供程序提供的行。 
    
5. 对于每个行从**HrQueryAllRows**返回：
    
    1. 传递给[IMAPISession::OpenEntry](imapisession-openentry.md)打开传输提供程序的状态对象**PR_ENTRYID**列。 
        
    2. 检查传输状态对象支持**FlushQueues**方法，通过检查其**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性具有 STATUS_FLUSH_QUEUES 标记设置。 
        
    3. 如果受支持，调用[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)。 如果不受支持，调用 MAPI 后台处理程序的**IMAPIStatus::FlushQueues**方法，传递_lpTargetTransport_参数中的传输类型的项标识符。 有关访问 MAPI 后台处理程序的状态的对象，请参阅前面过程的说明。 FLUSH_DOWNLOAD 标志以刷新传出队列或 FLUSH_UPLOAD 标志以刷新传入的队列设置。 
        
    4. 释放状态对象和状态表，以及分配表的[SRowSet](srowset.md)结构。 
    
大多数 LAN 传输提供程序一样，MAPI 后台处理程序采用 FLUSH_NO_UI 标志。 但是，并非所有传输提供程序都排定此标志，尤其是那些明确使用调制解调器和远程访问服务 (RAS)。 RAS 不旨在使客户端可以隐藏用户界面。 很可能为进行配置，以便其可以连接而无需交互的用户，但它是变得比较困难，需要精通客户端的消息服务的客户端。
  

