---
title: 关闭服务提供商
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e518830b-0aaa-4ce4-a85a-07e4f00750a9
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 4e25dad1e04927e10af38cdfbf8f30c9bd04234b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339205"
---
# <a name="shutting-down-a-service-provider"></a>关闭服务提供商

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端调用 [IMAPISession：：Logoff](imapisession-logoff.md) 方法结束会话并关闭所有活动服务提供商时，MAPI 反过来会调用以下方法： 
  
- [通讯簿提供程序的 IABLogon：：Logoff。](iablogon-logoff.md) 
    
- [消息存储提供程序的 IMSLogon：：Logoff。](imslogon-logoff.md) 
    
- [传输提供程序的 IXPLogon：：TransportLogoff。](ixplogon-transportlogoff.md) 
    
这些方法具有类似的实现。 注销方法执行的主要任务如下：
  
- 释放所有打开的对象，包括子对象和状态对象。
    
- 调用支持对象的 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法来缩小其引用计数。 
    
- 删除所有提供商注册的 [MAPIUID](mapiuid.md) 结构。 
    
- 删除状态表中的提供程序行。
    
- 执行与清理资源相关的任何任务，例如：
    
  - 终止与远程服务器的连接。
    
  - 缩小登录对象的引用计数。
    
  - 从提供程序存储的登录对象列表中删除登录对象。
    
  - 在调试模式下，发出跟踪以查找已泄漏内存的对象。
    
当 logoff 方法返回时，MAPI 将调用以下内容：
  
- 您的登录对象的 **IUnknown：：Release** 方法。 
    
- 提供程序对象的 **Shutdown** 方法，用于执行任何最终清理任务。 根据提供程序的类型，调用以下方法之一： 
    
  - [用于通讯簿提供程序的 IABProvider：：Shutdown](iabprovider-shutdown.md) 
    
  - [IMSProvider：：关闭](imsprovider-shutdown.md) 邮件存储提供程序 
    
  - [适用于传输提供程序的 IXPProvider：：Shutdown](ixpprovider-shutdown.md) 
    
- 提供程序对象的 **IUnknown：：Release** 方法。 
    
如果您的提供程序是邮件存储，则客户端对 [IMsgStore：：StoreLogoff](imsgstore-storelogoff.md) 的调用也将启动关闭过程。 **StoreLogoff** 关闭一个特定的邮件存储提供程序，并且对会话没有影响。 使用此方法只能关闭邮件存储提供程序;没有明确的方法可以关闭特定的通讯簿或传输提供程序。 若要了解如何响应 **StoreLogoff** 调用，请参阅 [关闭邮件存储提供程序](shutting-down-a-message-store-provider.md)。
  
当 MAPI 调用 Win32 API 函数 **FreeLibrary** 时，将卸载提供程序的 DLL，这是在上一个活动客户端调用 [MAPIUninitialize](mapiuninitialize.md)之后进行调用。 此时，您的服务提供商将已完成关闭。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

