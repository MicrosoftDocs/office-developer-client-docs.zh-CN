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
  
如果您的提供程序是邮件存储提供程序，则可以通过以下方法之一将其关闭：
  
- 当客户端或 MAPI 后台处理程序调用 [IMsgStore：：StoreLogoff 时](imsgstore-storelogoff.md)。 使用 **StoreLogoff** 关闭邮件存储提供程序会导致以有序且受控的方式关闭。 
    
- 当客户端调用 [IMAPISession：：Logoff 时](imapisession-logoff.md)。 
    
**IMsgStore：：StoreLogoff** 的实现应首先调用 [IMAPISupport：：StoreLogoffTransports](imapisupport-storelogofftransports.md)以通知 MAPI 它正在关闭，指示应注销任何相关传输提供程序。 当 **IMsgStore：：StoreLogoff** 返回时，其调用方将调用邮件存储的 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法。 通过调用 **支持** 对象的 **IUnknown：：Release** 方法实现此 Release 方法。 
  
MAPI 在邮件存储的 **IUnknown：：Release** 实现中执行以下任务： 
  
1. 删除邮件存储提供程序注册的所有 [MAPIUID](mapiuid.md) 结构。 
    
2. 从状态表中删除邮件存储提供程序的行。
    
3. 调用 [IMSLogon：：Logoff](imslogon-logoff.md) 以释放所有打开的对象、子对象和状态对象。 
    
4. 调用 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 以释放邮件存储提供程序的登录对象。 
    
某些客户端可能会省略 **对 IMsgStore：：StoreLogoff** 的调用，通过调用邮件存储的 **IUnknown：：Release** 方法来启动邮件存储提供程序的关闭。 在这些情况下，如果不调用 **StoreLogoff，** 则关闭将不太有序和受控。 编写邮件存储的 **Release** 方法以处理此可能性并跟踪是否已调用 **IMAPISupport：：StoreLogoffTransports。** **必须在关闭过程中调用 StoreLogoffTransports** 一次。 如果在 Release 方法中检测到尚未调用 **StoreLogoffTransports，** 则使用 LOGOFF_ABORT 调用它。 
  
## <a name="see-also"></a>另请参阅



[关闭服务提供商](shutting-down-a-service-provider.md)

