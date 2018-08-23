---
title: 关闭服务提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e518830b-0aaa-4ce4-a85a-07e4f00750a9
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: 70db0b0a62568cc499cf915634756bb422ae82ca
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567193"
---
# <a name="shutting-down-a-service-provider"></a>关闭服务提供程序

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当客户端调用[IMAPISession::Logoff](imapisession-logoff.md)方法来结束会话并关闭所有活动服务提供商时，MAPI 轮流调用以下方法： 
  
- [IABLogon::Logoff](iablogon-logoff.md)地址簿提供程序。 
    
- [IMSLogon::Logoff](imslogon-logoff.md)消息存储提供程序。 
    
- [IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)传输提供程序。 
    
这些方法具有类似的实现。 Logoff 方法执行的主要任务如下所示：
  
- 释放所有打开的对象，包括子对象和状态对象。
    
- 调用支持对象的[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法，以减少引用计数。 
    
- 删除所有提供商的注册[MAPIUID](mapiuid.md)结构。 
    
- 在状态表中删除提供程序的行。
    
- 执行与清理资源，如以下任何任务：
    
  - 终止与远程服务器的连接。
    
  - 递减引用计数登录对象。
    
  - 从您的提供程序存储的登录对象的列表中删除登录对象。
    
  - 在调试模式下，发出跟踪以查找已泄露内存的对象。
    
注销方法返回时，MAPI 调用下列：
  
- 登录对象的**IUnknown::Release**方法。 
    
- 提供程序对象的**Shutdown**方法执行任何最终清理任务。 根据您的提供程序的类型，调用以下方法之一： 
    
  - [IABProvider::Shutdown](iabprovider-shutdown.md)地址簿提供程序 
    
  - [IMSProvider::Shutdown](imsprovider-shutdown.md)消息存储提供程序 
    
  - [IXPProvider::Shutdown](ixpprovider-shutdown.md)传输提供程序 
    
- 提供程序对象的**IUnknown::Release**方法。 
    
如果您的提供商的消息存储，客户端调用[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)还将启动关机过程。 **StoreLogoff**关闭一个特定消息存储提供程序，并不影响会话。 仅消息存储提供程序可以使用此方法; 关闭没有明确的方式可以关闭特定地址簿或传输提供程序。 有关如何响应**StoreLogoff**呼叫，请参阅[关机的情况下消息存储提供程序](shutting-down-a-message-store-provider.md)。
  
MAPI 呼叫 Win32 API 函数**句**，最后一个活动的客户端具有调用[MAPIUninitialize](mapiuninitialize.md)后进行的呼叫时，将卸载提供程序的 DLL。 此时，由服务提供商将完成关机的情况下。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

