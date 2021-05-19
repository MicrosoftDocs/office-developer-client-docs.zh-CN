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
  
客户端可以在初始化过程中注册通讯簿或邮件存储通知。
  
MAPI 支持通讯簿上的通知，而不管是否有通讯簿提供程序支持它。 对邮件存储通知的支持取决于特定邮件存储提供程序。 若要确定特定邮件存储提供程序是否支持通知，请检查其PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。  如果邮件存储支持通知，STORE_NOTIFY_OK位。 
  
通过调用建议源对象的 Advise 方法注册 **通知** 。 许多对象都 **实现了 Advise，** 客户端可以通过多种方式向这些对象注册。 
  
 **注册通知**
  
1. 创建 MAPI 建议接收对象并递增其引用计数。
    
2. 如果合适，请调用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 创建包装原始建议接收器的建议接收对象，然后释放原始建议接收器。 
    
3. 调用下列 Advise **方法之** 一以完成注册： 
    
  - 调用 [IMAPISession：：Advise](imapisession-advise.md) 以注册会话通知或在通讯簿或邮件存储对象上注册通知。 
    
  - 调用 [IAddrBook：：Advise](iaddrbook-advise.md) 注册通讯簿通知或在邮件用户、容器或通讯组列表上注册通知。 
    
  - 调用 [IABLogon：：Advise](iablogon-advise.md) 以直接在通讯簿提供程序中注册，以接收有关邮件用户、容器或通讯组列表的通知。 
    
  - 调用 [IMsgStore：：Advise](imsgstore-advise.md) 以注册邮件存储通知或文件夹或邮件上的通知。 
    
  - 调用 [IMSLogon：：Advise](imslogon-advise.md) 以直接向邮件存储提供程序注册，以接收有关文件夹或邮件的通知。 
    
  - 调用 [IMAPITable：：Advise](imapitable-advise.md) 以注册表通知。 
    
4. 缓存从 Advise 返回的连接 **号**。
    
5. 如果使用包装的建议接收器，请释放它。 注册包装的建议接收器后，你不再需要它。
    
调用 ** IMAPISession：：Advise ** 使你能够注册整个会话上的关键错误通知或单个对象上的各种通知。 当使用共享会话的另一个客户端调用 [IMAPISession：：Logoff](imapisession-logoff.md) 方法时，会话会向登录到共享会话的客户端发送关键错误通知。 若要注册会话通知，请为条目标识符参数传递 NULL。 若要在单个对象上注册通知，请传递对象的条目标识符。 **IMAPISession** 方法将调用转发到相应的服务提供商，由条目标识符的 **MAPIUID** 部分确定。 调用 **IMAPISession：：Advise** 注册对象通知比调用服务提供商的 Advise 方法 **更简单** 。 
  
在通讯簿中注册类似于向会话注册。 若要注册通讯簿中的关键错误通知，请为条目标识符传递 NULL。 若要注册特定通讯簿对象上的通知，请指定相应的条目标识符和感兴趣的事件。 请注意，许多通讯簿提供程序不支持有关单个对象的通知。 相反，它们支持有关其内容和层次结构表的表通知。 
  
最佳做法是在 Advise 调用成功返回后立即释放您通过 [HrAllocAdviseSink](hrallocadvisesink.md) 实现或创建的 **通知** 接收器。 这是因为服务提供商可以先在 **Advise** 调用之后，但在进行 **Unadvise** 调用之前释放通知接收器。 一旦向建议源提供指向建议接收器的指针，并且引用计数已针对此建议接收器递增，那么除非长期使用，否则应释放它。 
  
> [!NOTE]
> 在调用 **Unadvise** 之前，不会释放表示有效咨询注册的所有连接号码。 
  

