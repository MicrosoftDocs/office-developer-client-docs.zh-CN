---
title: 注册通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 45625387-dbd2-4ca8-926b-ef87998d01d7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ccc2758b59a9227afbc50360102e793892bbdc52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424901"
---
# <a name="registering-for-a-notification"></a>注册通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可以将通讯簿或邮件存储通知注册为其初始化过程的一部分。
  
MAPI 支持对通讯簿发出通知, 而不管通讯簿提供程序是否支持它。 对邮件存储区的通知支持取决于特定的邮件存储提供程序。 若要确定特定的邮件存储提供程序是否支持通知, 请检查其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。 如果邮件存储区支持通知, 则将设置 STORE_NOTIFY_OK 位。 
  
通过调用通知源对象的**advise**方法注册通知。 许多对象都实现了**建议**, 客户端可以通过多种方式向这些对象注册。 
  
 **注册通知**
  
1. 创建一个 MAPI 建议接收器对象并增加其引用计数。
    
2. 如果需要, 请调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)以创建一个包装原始通知接收器的建议接收器对象, 然后释放原始的建议接收器。 
    
3. 调用以下 "**建议**" 方法之一以完成注册: 
    
  - 调用[IMAPISession:: 建议](imapisession-advise.md)注册会话通知或通讯簿或邮件存储对象上的通知。 
    
  - 调用[IAddrBook:: 建议](iaddrbook-advise.md)注册通讯簿通知或邮件用户、容器或通讯组列表上的通知。 
    
  - 调用[IABLogon:: 建议](iablogon-advise.md)直接为邮件用户、容器或通讯组列表上的通知注册通讯簿提供程序。 
    
  - 调用[IMsgStore:: 建议](imsgstore-advise.md)注册邮件存储通知或文件夹或邮件上的通知。 
    
  - 调用[IMSLogon:: 建议](imslogon-advise.md)直接向邮件存储提供程序注册文件夹或邮件中的通知。 
    
  - 调用[IMAPITable:: 建议](imapitable-advise.md)注册表通知。 
    
4. 缓存从**Advise**返回的连接号码。
    
5. 如果使用包装的建议接收器, 请将其释放。 在注册了包装的通知接收器之后, 您将不再需要它。
    
通过调用 * * IMAPISession:: Advise * *, 可以在整个会话或针对单个对象的各种通知中注册关键错误通知。 会话向登录到共享会话的客户端发送关键错误通知。当另一个客户端使用共享会话时, 将调用[IMAPISession:: 注销](imapisession-logoff.md)方法。 若要注册会话通知, 请为条目标识符参数传递 NULL。 若要在单个对象上注册通知, 请传递对象的条目标识符。 **IMAPISession**方法将调用转发给相应的服务提供程序, 由条目标识符的**MAPIUID**部分确定。 调用**IMAPISession:: 建议**注册对象通知比调用服务提供商的**建议**方法更简单。 
  
使用通讯簿注册类似于在会话中注册。 若要从通讯簿中注册关键错误通知, 请为条目标识符传递 NULL。 若要在特定的通讯簿对象上注册通知, 请指定适当的条目标识符和事件或相关事件。 请注意, 许多通讯簿提供程序不支持单个对象上的通知。 相反, 它们支持对其内容和层次结构表的表通知。 
  
最佳做法是, 在成功返回**通知**调用之后, 释放在[HrAllocAdviseSink](hrallocadvisesink.md)中实现或创建的通知接收器。 这是因为, 服务提供商在发出**通知**调用之后, 但在进行**Unadvise**调用之前, 可以发布您的通知接收器。 在此通知接收器上为通知源提供指向通知接收器和引用计数的指针后, 最好将其释放, 除非您对其使用长期。 
  
> [!NOTE]
> 在进行**Unadvise**呼叫之前, 将不会发布表示有效的咨询注册的所有连接号码。 
  

