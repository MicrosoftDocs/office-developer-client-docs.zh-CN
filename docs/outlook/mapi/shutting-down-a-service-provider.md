---
title: 关闭服务提供程序
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
# <a name="shutting-down-a-service-provider"></a>关闭服务提供程序

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端调用[IMAPISession:: 注销](imapisession-logoff.md)方法以结束会话并关闭所有活动服务提供程序时, MAPI 将调用以下方法: 
  
- [IABLogon::](iablogon-logoff.md)通讯簿提供程序的注销。 
    
- [IMSLogon::](imslogon-logoff.md)邮件存储提供程序的注销。 
    
- [IXPLogon:: TransportLogoff](ixplogon-transportlogoff.md)的传输提供程序。 
    
这些方法具有类似的实现。 注销方法执行的主要任务如下所示:
  
- 释放所有打开的对象, 包括子对象和状态对象。
    
- 调用支持对象的[IUnknown:: Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法以递减其引用计数。 
    
- 删除提供程序的所有已注册[MAPIUID](mapiuid.md)结构。 
    
- 在状态表中删除提供程序的行。
    
- 执行与清理资源相关的任何任务, 如下所示:
    
  - 终止与远程服务器的连接。
    
  - 递减登录对象上的引用计数。
    
  - 从提供程序存储的登录对象列表中删除 "登录" 对象。
    
  - 在调试模式下, 发出跟踪以查找具有泄漏内存的对象。
    
当您的注销方法返回时, MAPI 将调用以下内容:
  
- 您的登录对象的**IUnknown:: Release**方法。 
    
- 提供程序对象的**关闭**方法以执行任何最终清理任务。 根据您的提供程序的类型, 将调用以下方法之一: 
    
  - [IABProvider::](iabprovider-shutdown.md)针对通讯簿提供程序的关闭 
    
  - [IMSProvider:: Shutdown](imsprovider-shutdown.md) for 邮件存储提供程序 
    
  - [IXPProvider::](ixpprovider-shutdown.md)针对传输提供程序的关闭 
    
- 提供程序对象的**IUnknown:: Release**方法。 
    
如果提供程序是邮件存储区, 则客户端对[IMsgStore:: StoreLogoff](imsgstore-storelogoff.md)的调用也将启动关闭过程。 **StoreLogoff**关闭一个特定的邮件存储提供程序, 并且不会对该会话产生影响。 使用此方法时, 仅可关闭邮件存储提供程序。没有显式关闭特定通讯簿或传输提供程序的方法。 有关如何响应**StoreLogoff**呼叫的信息, 请参阅[关闭邮件存储提供程序](shutting-down-a-message-store-provider.md)。
  
当 MAPI 调用 Win32 API 函数**FreeLibrary**时, 将卸载提供程序的 DLL (在最后一个活动客户端调用[MAPIUninitialize](mapiuninitialize.md)之后进行的调用)。 这次, 服务提供商将完成关闭。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

