---
title: 关闭邮件存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e38219db-f867-4c1d-9973-0e025779e8b6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8e4712572eaff465bb23b55eccc3670f637c0f9c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339198"
---
# <a name="shutting-down-a-message-store-provider"></a>关闭邮件存储提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果提供程序是邮件存储提供程序, 则可以通过下列方式之一将其关闭:
  
- 当客户端或 MAPI 后台处理程序调用[IMsgStore:: StoreLogoff](imsgstore-storelogoff.md)时。 使用**StoreLogoff**关闭邮件存储提供程序会导致以有序且可控的方式进行关闭。 
    
- 当客户端调用[IMAPISession:: 注销](imapisession-logoff.md)时。 
    
您的**IMsgStore:: StoreLogoff**的实现应首先调用[IMAPISupport:: StoreLogoffTransports](imapisupport-storelogofftransports.md) , 以通知 MAPI 它正在关闭, 表明应注销任何相关的传输提供程序。 当**IMsgStore:: StoreLogoff**返回时, 其调用方将调用您的邮件存储区的[IUnknown:: Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法。 通过调用支持对象的**IUnknown:: Release**方法实现此**Release**方法。 
  
MAPI 在其 IUnknown 实施中执行以下任务 **:: Release** for message 书店: 
  
1. 删除由邮件存储区提供程序注册的所有[MAPIUID](mapiuid.md)结构。 
    
2. 从状态表中删除邮件存储提供程序的行。
    
3. 调用[IMSLogon:: 注销](imslogon-logoff.md)以释放所有打开的对象、子对象和状态对象。 
    
4. 调用[IUnknown:: release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)以释放邮件存储区提供程序的登录对象。 
    
某些客户端可能会省略对**IMsgStore:: StoreLogoff**的调用, 从而启动对邮件存储提供程序的调用, 并对邮件存储区的**IUnknown:: Release**方法进行关闭。 在这些情况下, 在不调用**StoreLogoff**的情况下会发生关机, 且控制程度较低。 编写消息存储库的**Release**方法以处理这种可能性, 并跟踪是否发生了对**IMAPISupport:: StoreLogoffTransports**的调用。 在关闭过程中, 必须调用一次**StoreLogoffTransports** 。 如果在您的**Release**方法中检测到尚未调用**StoreLogoffTransports** , 请使用 LOGOFF_ABORT 标志对其进行调用。 
  
## <a name="see-also"></a>另请参阅



[关闭服务提供程序](shutting-down-a-service-provider.md)

