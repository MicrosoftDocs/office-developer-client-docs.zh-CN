---
title: 按需发送或接收邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 479404c5-4926-402a-aa12-75dd23276d75
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 15b9c8c5a56b6f37464d2469bd1d7b3e24596502
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356474"
---
# <a name="sending-or-receiving-a-message-on-demand"></a>按需发送或接收邮件
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端通常依赖 mapi 子系统 (mapi 后台处理程序和服务提供程序) 来处理邮件传输和接收的时间。 但是, 可以使用 MAPI 后台处理程序或传输提供程序的 status 对象来更改此计时。
  
[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法从一个或多个传输提供程序的传入或传出队列中删除所有邮件。 以下过程介绍了两种用于按需发送或接收邮件的技术。 第一个过程使用 MAPI 后台处理程序的状态对象刷新配置文件中的每个传输提供程序的队列;第二个过程刷新单个传输提供程序的队列。 
  
### <a name="to-flush-all-incoming-or-outgoing-queues-in-a-single-operation"></a>在单个操作中刷新所有传入或传出队列
  
1. 调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问状态表。 
    
2. 调用状态表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法来限制将列设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md))。
    
3. 使用[SPropertyRestriction](spropertyrestriction.md)结构生成属性限制, 以将**PR_RESOURCE_TYPE**与 MAPI_SPOOLER 相匹配。 
    
4. 调用[HrQueryAllRows](hrqueryallrows.md), 在**SPropertyRestriction**结构中传递, 以检索代表 MAPI 后台处理程序状态的行。 
    
5. 将**PR_ENTRYID**列传递给[IMAPISession:: OpenEntry](imapisession-openentry.md)以打开 MAPI 后台处理程序的状态对象。 
    
6. 调用 MAPI 后台处理程序的[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法, 传递 FLUSH_NO_UI 标志以禁止显示用户界面, 并选择 FLUSH_DOWNLOAD 或 FLUSH_UPLOAD 标志以刷新传出或传入队列。 
    
7. 释放状态对象和状态表, 以及为该表分配的[SRowSet](srowset.md)结构。 
    
### <a name="to-flush-incoming-or-outgoing-queues-individually-by-transport-provider"></a>通过传输提供程序单独刷新传入或传出队列
  
1. 调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问状态表。 
    
2. 调用状态表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法以将列设置限制为**PR_ENTRYID**和**PR_RESOURCE_TYPE**。
    
3. 使用[SPropertyRestriction](spropertyrestriction.md)结构生成属性限制, 以将**PR_RESOURCE_TYPE**与 MAPI_TRANSPORT_PROVIDER 相匹配。 
    
4. 调用[HrQueryAllRows](hrqueryallrows.md), 在**SPropertyRestriction**结构中传递, 以检索传输提供程序提供的行。 
    
5. 对于从**HrQueryAllRows**返回的每个行:
    
    1. 将**PR_ENTRYID**列传递给[IMAPISession:: OpenEntry](imapisession-openentry.md)以打开传输提供程序的状态对象。 
        
    2. 检查传输状态对象是否支持**FlushQueues**方法, 方法是检查其**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性是否设置了 STATUS_FLUSH_QUEUES 标志。 
        
    3. 如果支持, 请调用[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)。 如果不受支持, 请调用 MAPI 后台处理程序的**IMAPIStatus:: FlushQueues**方法, 并在_lpTargetTransport_参数中传递传输条目标识符。 有关访问 MAPI 后台处理程序的状态对象的说明, 请参阅前面的过程。 设置 FLUSH_DOWNLOAD 标志以刷新传出队列或 FLUSH_UPLOAD 标志以刷新传入队列。 
        
    4. 释放状态对象和状态表, 以及为该表分配的[SRowSet](srowset.md)结构。 
    
MAPI 后台处理程序将 FLUSH_NO_UI 标志视为大多数 LAN 传输提供程序。 但是, 并不是所有传输提供者都服从此标志, 尤其是那些显式使用调制解调器和远程访问服务 (RAS) 的。 RAS 不允许客户端禁止显示用户界面。 客户端可以进行配置, 以便它可以在不需要用户交互的情况下进行连接, 但这很困难, 需要了解客户端的邮件服务。
  

