---
title: 注册通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 45625387-dbd2-4ca8-926b-ef87998d01d7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5a35add66fb685b3c17464269456edf6b456711e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570210"
---
# <a name="registering-for-a-notification"></a>注册通知

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端可以通讯簿或消息存储通知注册为其初始化过程的一部分。
  
MAPI 支持在通讯簿无论是否任何通讯簿提供程序支持通知。 消息存储区上的通知的支持取决于特定消息存储提供程序。 若要确定特定消息存储提供程序是否支持通知，请查看其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。 如果消息存储库支持通知，将设置 STORE_NOTIFY_OK 位。 
  
通过调用 advise 源对象的**Advise**方法注册通知。 许多对象实现**Advise**和客户端可以注册这些对象中的各种方式。 
  
 **通知注册**
  
1. 创建 MAPI 告知接收器对象和增加其引用计数。
    
2. 如果合适，呼叫[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)创建您的原始通知接收器的换行 advise 接收器对象然后释放原始建议接收器。. 
    
3. 调用以下的**Advise**方法，以完成注册之一： 
    
  - 调用[IMAPISession::Advise](imapisession-advise.md)注册会话通知或通讯簿或消息存储对象上的通知。 
    
  - 调用[IAddrBook::Advise](iaddrbook-advise.md)注册地址簿通知或消息的用户、 容器或通讯组列表上的通知。 
    
  - 调用[IABLogon::Advise](iablogon-advise.md)可直接注册通知消息的用户、 容器或通讯组列表上的通讯簿提供程序。 
    
  - 调用[IMsgStore::Advise](imsgstore-advise.md)注册消息存储通知或文件夹或消息的通知。 
    
  - 调用[IMSLogon::Advise](imslogon-advise.md)可直接注册的消息存储提供程序上的文件夹或消息的通知。 
    
  - 调用[IMAPITable::Advise](imapitable-advise.md)注册表通知。 
    
4. 缓存从**Advise**返回连接数。
    
5. 如果使用换行的通知接收器，请将其释放。 换行的通知接收器注册后，您不再需要它。
    
调用 * * IMAPISession::Advise * * 使您能够注册总体会话上的错误通知，或在单个对象的各种通知。 会话将严重错误通知发送到客户端登录到共享会话时使用的共享的会话的另一个客户端调用[IMAPISession::Logoff](imapisession-logoff.md)方法。 若要注册会话通知，请为条目标识符参数传递 NULL。 若要注册的单个对象上的通知，请传递对象的项标识符。 **IMAPISession**方法转发到适当的服务提供程序，呼叫与由的项标识符的**MAPIUID**部分。 调用**IMAPISession::Advise**注册对象通知是比调用服务提供商的**Advise**方法更简单。 
  
注册通讯簿等同于注册会话。 若要注册的通讯簿中的错误通知，请为条目标识符传递 NULL。 若要注册特定地址簿对象上的通知，请指定适当的项标识符和事件或感兴趣的事件。 请注意，许多通讯簿提供程序不支持通知上单个对象。 相反，它们在其内容和层次结构表支持表通知。 
  
很好的做法发行版的实现，或使用[HrAllocAdviseSink](hrallocadvisesink.md) **Advise**调用的成功返回后立即创建通知接收器。 这是因为可能为服务提供商释放通知接收器在**Advise**调用后，但之前**Unadvise**进行调用。 一旦您已指定 advise 源指针到通知接收器，在此通知接收器上会增加引用计数，最好其释放，除非您有长期使用它。 
  
> [!NOTE]
> 直到**Unadvise**调用，并不会释放表示有效顾问注册的所有连接号码。 
  

