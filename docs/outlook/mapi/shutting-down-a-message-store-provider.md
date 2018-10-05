---
title: 关闭邮件存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e38219db-f867-4c1d-9973-0e025779e8b6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8e4712572eaff465bb23b55eccc3670f637c0f9c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386052"
---
# <a name="shutting-down-a-message-store-provider"></a>关闭邮件存储区提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果您的提供商消息存储提供程序，它可以关闭通过以下方式之一：
  
- 当客户端或 MAPI 后台处理程序调用[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)。 关机的情况下**StoreLogoff**的消息存储提供程序使关闭发生有序、 控制更严格的方式。 
    
- 当客户端调用[IMAPISession::Logoff](imapisession-logoff.md)。 
    
**IMsgStore::StoreLogoff**的实现应首先调用[IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md) ，告知 MAPI，它将被关闭，指示应记录的任何相关的传输提供程序。 **IMsgStore::StoreLogoff**返回时，其呼叫者将调用您的消息存储[IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法。 通过调用支持对象的**IUnknown::Release**方法实现此**发行版**方法。 
  
MAPI 的消息存储**IUnknown::Release**其实现中执行以下任务： 
  
1. 删除所有注册的消息存储提供程序的[MAPIUID](mapiuid.md)结构。 
    
2. 从状态表中删除的消息存储提供程序的行。
    
3. 调用[IMSLogon::Logoff](imslogon-logoff.md)释放所有打开的对象、 子对象和状态对象。 
    
4. 调用[IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)释放消息存储提供程序的登录对象。 
    
某些客户端可能会省略**IMsgStore::StoreLogoff**，启动关闭消息存储提供程序的消息存储**IUnknown::Release**方法调用的调用。 在这些情况下不**StoreLogoff**调用的情况下关闭是较低序和控制。 编写消息存储库**版本**方法，以处理这种可能性和跟踪发生**IMAPISupport::StoreLogoffTransports**调用。 必须关闭过程中一次调用**StoreLogoffTransports** 。 如果在您的**发布**方法中检测**StoreLogoffTransports**尚未调用，调用了 LOGOFF_ABORT 标记。 
  
## <a name="see-also"></a>另请参阅



[关闭服务提供程序](shutting-down-a-service-provider.md)

